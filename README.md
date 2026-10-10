<div align="center">

<img src="./assets/header.svg" alt="Terminal: whoami → Lars Stimpel · Data Engineering &amp; DevOps" width="100%"/>

<br/>

<a href="https://larsstimpel.de"><img src="https://img.shields.io/badge/larsstimpel.de-portfolio-7ee787?style=for-the-badge&logo=astro&logoColor=white&labelColor=0d1117" alt="Portfolio"/></a>
<a href="https://www.linkedin.com/in/larsstimpel"><img src="https://img.shields.io/badge/LinkedIn-Lars_Stimpel-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=0d1117" alt="LinkedIn"/></a>
<a href="mailto:l_stimpel@web.de"><img src="https://img.shields.io/badge/Mail-schreib_mir-d2a8ff?style=for-the-badge&logo=maildotru&logoColor=white&labelColor=0d1117" alt="E-Mail"/></a>
<img src="https://komarev.com/ghpvc/?username=larsskrachen&style=for-the-badge&color=79c0ff&label=profilaufrufe" alt="Profilaufrufe"/>

</div>

---

### `$ cat ueber-mich.yaml`

```yaml
name:      Lars Stimpel
rolle:     Data & DevOps Engineer Consultant @ RedArcs Consulting
standort:  Ingolstadt / München
fokus:     [Datenplattformen, CI/CD, Cloud]
mission:   Ich baue Datenpipelines und die Infrastruktur, auf der sie laufen.

definition_of_done:        # eine Pipeline ist erst fertig, wenn sie …
  - Tests hat
  - automatisch ausgerollt wird
  - überwacht ist, damit ich sehe, ob sie läuft

prinzipien:
  - Lösungen lieber einfach halten
  - Doku so schreiben, dass andere damit weiterarbeiten können
  - neue Tools an echten Problemen testen – manches auch einfach aus Neugier
```

### `$ dbt ls --select pipeline+` &nbsp;<sub>— mein Stack, Schicht für Schicht</sub>

```mermaid
flowchart TB
    O{{04 · Orchestrierung<br/>Airflow}} -.steuert.-> P
    subgraph P[Datenpipeline]
      direction LR
      I[01 · Ingest<br/>Kafka · Debezium] --> S[(02 · Storage<br/>Iceberg · Delta · StarRocks)]
      S --> T[03 · Transform<br/>dbt · Python · SQL]
      T --> A[05 · Apps & BI<br/>Superset · Vue · Java]
      A --> X([Output ✨])
    end
    P -.läuft auf.-> F
    subgraph F[Fundament]
      direction LR
      C[06 · Infra & CI/CD<br/>Terraform · K8s · Argo CD] ~~~ K[07 · Security<br/>Keycloak · OpenBao] ~~~ M[08 · Observability<br/>Prometheus · Grafana]
    end
```

<table>
<tr><td><code>01</code></td><td><b>Ingest</b><br/><sub>Daten dort abholen, wo sie entstehen – per CDC, Event-Stream oder API.</sub></td><td><img src="https://img.shields.io/badge/Kafka-231F20?style=flat-square&labelColor=0d1117&logo=apachekafka&logoColor=white" alt="Kafka"/> <img src="https://img.shields.io/badge/AutoMQ-4F46E5?style=flat-square&labelColor=0d1117" alt="AutoMQ"/> <img src="https://img.shields.io/badge/Debezium-91D443?style=flat-square&labelColor=0d1117" alt="Debezium"/> <img src="https://img.shields.io/badge/REST_APIs-009688?style=flat-square&labelColor=0d1117&logo=openapiinitiative&logoColor=white" alt="REST APIs"/></td></tr>
<tr><td><code>02</code></td><td><b>Storage</b><br/><sub>Offene Tabellenformate: festes Schema, Time Travel, Rollback.</sub></td><td><img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&labelColor=0d1117&logo=postgresql&logoColor=white" alt="PostgreSQL"/> <img src="https://img.shields.io/badge/CloudNativePG-4169E1?style=flat-square&labelColor=0d1117&logo=postgresql&logoColor=white" alt="CloudNativePG"/> <img src="https://img.shields.io/badge/S3-569A31?style=flat-square&labelColor=0d1117&logo=amazons3&logoColor=white" alt="S3"/> <img src="https://img.shields.io/badge/RustFS-B7410E?style=flat-square&labelColor=0d1117&logo=rust&logoColor=white" alt="RustFS"/> <img src="https://img.shields.io/badge/Delta_Lake-00ADD4?style=flat-square&labelColor=0d1117" alt="Delta Lake"/> <img src="https://img.shields.io/badge/Apache_Iceberg-3A6DB5?style=flat-square&labelColor=0d1117" alt="Apache Iceberg"/> <img src="https://img.shields.io/badge/StarRocks-5A67D8?style=flat-square&labelColor=0d1117" alt="StarRocks"/></td></tr>
<tr><td><code>03</code></td><td><b>Transform</b><br/><sub>Rohdaten → Tabellen, mit denen andere arbeiten können. Versioniert, getestet, mit Lineage.</sub></td><td><img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&labelColor=0d1117&logo=python&logoColor=white" alt="Python"/> <img src="https://img.shields.io/badge/SQL-CC2927?style=flat-square&labelColor=0d1117" alt="SQL"/> <img src="https://img.shields.io/badge/dbt_%E2%9C%93_zertifiziert-FF694B?style=flat-square&labelColor=0d1117&logo=dbt&logoColor=white" alt="dbt ✓ zertifiziert"/> <img src="https://img.shields.io/badge/Kafka_Streams-231F20?style=flat-square&labelColor=0d1117&logo=apachekafka&logoColor=white" alt="Kafka Streams"/></td></tr>
<tr><td><code>04</code></td><td><b>Orchestrierung</b><br/><sub>Richtige Reihenfolge, Retries – und eine Nachricht, wenn's nicht hilft.</sub></td><td><img src="https://img.shields.io/badge/Apache_Airflow-017CEE?style=flat-square&labelColor=0d1117&logo=apacheairflow&logoColor=white" alt="Apache Airflow"/></td></tr>
<tr><td><code>05</code></td><td><b>Apps & BI</b><br/><sub>Wo Daten bei den Menschen ankommen.</sub></td><td><img src="https://img.shields.io/badge/Apache_Superset-20A6C9?style=flat-square&labelColor=0d1117&logo=apachesuperset&logoColor=white" alt="Apache Superset"/> <img src="https://img.shields.io/badge/Vue.js-4FC08D?style=flat-square&labelColor=0d1117&logo=vuedotjs&logoColor=white" alt="Vue.js"/> <img src="https://img.shields.io/badge/TypeScript_/_JS-3178C6?style=flat-square&labelColor=0d1117&logo=typescript&logoColor=white" alt="TypeScript / JS"/> <img src="https://img.shields.io/badge/Java-ED8B00?style=flat-square&labelColor=0d1117&logo=openjdk&logoColor=white" alt="Java"/> <img src="https://img.shields.io/badge/Reactive_Java-6DB33F?style=flat-square&labelColor=0d1117" alt="Reactive Java"/></td></tr>
<tr><td><code>06</code></td><td><b>Infra & CI/CD</b><br/><sub>Infrastructure as Code, GitOps statt Handarbeit auf dem Server.</sub></td><td><img src="https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&labelColor=0d1117&logo=terraform&logoColor=white" alt="Terraform"/> <img src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&labelColor=0d1117&logo=kubernetes&logoColor=white" alt="Kubernetes"/> <img src="https://img.shields.io/badge/Helm-0F1689?style=flat-square&labelColor=0d1117&logo=helm&logoColor=white" alt="Helm"/> <img src="https://img.shields.io/badge/Kustomize-326CE5?style=flat-square&labelColor=0d1117" alt="Kustomize"/> <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&labelColor=0d1117&logo=docker&logoColor=white" alt="Docker"/> <img src="https://img.shields.io/badge/GitLab_CI-FC6D26?style=flat-square&labelColor=0d1117&logo=gitlab&logoColor=white" alt="GitLab CI"/> <img src="https://img.shields.io/badge/Argo_CD-EF7B4D?style=flat-square&labelColor=0d1117&logo=argo&logoColor=white" alt="Argo CD"/></td></tr>
<tr><td><code>07</code></td><td><b>Security & Identity</b><br/><sub>Zentrale Anmeldung, Secrets gehören nicht ins Repo.</sub></td><td><img src="https://img.shields.io/badge/Keycloak-4D4D4D?style=flat-square&labelColor=0d1117&logo=keycloak&logoColor=white" alt="Keycloak"/> <img src="https://img.shields.io/badge/Authentik-FD4B2D?style=flat-square&labelColor=0d1117&logo=authentik&logoColor=white" alt="Authentik"/> <img src="https://img.shields.io/badge/OpenBao_/_Vault-FFEC6E?style=flat-square&labelColor=0d1117&logo=vault&logoColor=white" alt="OpenBao / Vault"/></td></tr>
<tr><td><code>08</code></td><td><b>Observability</b><br/><sub>Sehen, dass etwas hakt – bevor es jemand anderem auffällt.</sub></td><td><img src="https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&labelColor=0d1117&logo=prometheus&logoColor=white" alt="Prometheus"/> <img src="https://img.shields.io/badge/Grafana-F46800?style=flat-square&labelColor=0d1117&logo=grafana&logoColor=white" alt="Grafana"/> <img src="https://img.shields.io/badge/VictoriaMetrics-621773?style=flat-square&labelColor=0d1117&logo=victoriametrics&logoColor=white" alt="VictoriaMetrics"/> <img src="https://img.shields.io/badge/OpenMetadata-7147E8?style=flat-square&labelColor=0d1117" alt="OpenMetadata"/></td></tr>
</table>

### `$ openssl verify -CAfile trust-store.pem lars.pem`

```diff
+ dbt Developer                              dbt Labs              ✓ gültig  05/2025 → 05/2027
+   Credential-ID: 143006453
! Certified Kubernetes Administrator (CKA)   The Linux Foundation  ⏳ in Arbeit
```

### `$ git log --graph --oneline --author="Lars Stimpel"`

```text
* 9fa1bf3 (HEAD -> main) Data & DevOps Engineer Consultant @ RedArcs Consulting   03/2025 – heute
|
* … ältere Commits: siehe LinkedIn
```

### `$ git log --graph --all` &nbsp;<sub>— mein Contribution-Graph, frisch verspeist</sub>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/larsskrachen/larsskrachen/output/snake-dark.svg"/>
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/larsskrachen/larsskrachen/output/snake.svg"/>
  <img alt="Contribution-Snake frisst meinen Commit-Graphen" src="https://raw.githubusercontent.com/larsskrachen/larsskrachen/output/snake.svg"/>
</picture>

### `$ ls ./öffentlich`

<p align="center">
  <a href="https://github.com/larsskrachen/find-in-files">
    <img src="https://img.shields.io/badge/find--in--files-TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white&labelColor=0d1117" alt="find-in-files"/>
  </a>
  <a href="https://github.com/larsskrachen/zsh_history">
    <img src="https://img.shields.io/badge/zsh__history-JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=white&labelColor=0d1117" alt="zsh_history"/>
  </a>
</p>

<details>
<summary><b>🥚 <code>$ sudo make me a sandwich</code></b></summary>

<br/>

```text
[sudo] Passwort für lars: ********
Okay. 🥪  (Deployment via Argo CD, Rollback jederzeit möglich.)
```

Wer einen 3D-Flug durch eine Datenpipeline sehen will: **[larsstimpel.de](https://larsstimpel.de)** 🚀

</details>

### `$ ./kontakt.sh`

Du hast eine Frage zu einem Projekt oder willst dich einfach fachlich austauschen?
Schreib mir eine [Mail](mailto:l_stimpel@web.de) oder eine Nachricht auf [LinkedIn](https://www.linkedin.com/in/larsstimpel).

<div align="center">
<img src="./assets/footer.svg" alt="exit 0 — danke fürs Vorbeischauen" width="100%"/>
</div>
