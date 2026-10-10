<div align="center">

<img src="./assets/header.svg" alt="Terminal: whoami → Lars · Developer · Data Engineering · Health-IT · Homelab" width="100%"/>

<br/>

<a href="https://github.com/larsskrachen?tab=repositories"><img src="https://img.shields.io/badge/repos-erkunden-79c0ff?style=for-the-badge&logo=github&logoColor=white&labelColor=0d1117" alt="Repos"/></a>
<a href="https://github.com/larsskrachen?tab=followers"><img src="https://img.shields.io/github/followers/larsskrachen?style=for-the-badge&logo=github&logoColor=white&label=followers&color=7ee787&labelColor=0d1117" alt="Followers"/></a>
<img src="https://komarev.com/ghpvc/?username=larsskrachen&style=for-the-badge&color=d2a8ff&label=profilaufrufe" alt="Profilaufrufe"/>

</div>

---

### `$ cat ueber-mich.md`

```yaml
name:      Lars
rolle:     Developer mit Hang zu Daten, Pipelines und sauberer Infrastruktur
fokus:
  - Data Engineering        # ETL/ELT, Change Data Capture, Orchestrierung
  - Health-IT               # HL7 CDA ➜ FHIR, XSLT-Transformationen, Interoperabilität
  - Privacy by Design       # Anonymisierung & verantwortungsvolle Datennutzung
  - Homelab                 # Infrastructure as Code, Self-Hosting, Tüfteln
gerade:    lerne ständig Neues – und schreibe es am liebsten gleich in Code
motto:     "Wenn du es zweimal machst, automatisiere es."
```

### `$ ls ./werkzeugkasten`

<p align="center">
  <img src="https://skillicons.dev/icons?i=java,py,ts,js,vue,astro,nodejs,html,css&perline=9" alt="Sprachen & Frameworks"/>
  <br/>
  <img src="https://skillicons.dev/icons?i=postgres,kafka,docker,terraform,linux,bash,git,githubactions,latex&perline=9" alt="Daten, Infra & Tools"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/HL7_FHIR-E34F26?style=flat-square&logo=fireship&logoColor=white" alt="HL7 FHIR"/>
  <img src="https://img.shields.io/badge/XSLT-8a2be2?style=flat-square&logo=xml&logoColor=white" alt="XSLT"/>
  <img src="https://img.shields.io/badge/Apache_Airflow-017CEE?style=flat-square&logo=apacheairflow&logoColor=white" alt="Apache Airflow"/>
  <img src="https://img.shields.io/badge/Debezium-91D443?style=flat-square&logo=apachekafka&logoColor=black" alt="Debezium"/>
  <img src="https://img.shields.io/badge/dlt-59C1D5?style=flat-square&logo=python&logoColor=white" alt="dlt"/>
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white" alt="Jupyter"/>
  <img src="https://img.shields.io/badge/Proxmox-E57000?style=flat-square&logo=proxmox&logoColor=white" alt="Proxmox"/>
</p>

### `$ cat pipeline.mmd` &nbsp;<sub>— so denke ich über Daten</sub>

```mermaid
flowchart LR
    A[(Quellsysteme)] -->|CDC / Debezium| B{{Kafka}}
    C[/HL7 CDA-Dokumente/] -->|XSLT| D[FHIR-Ressourcen]
    B --> E[ELT mit dlt & Airflow]
    D --> E
    E -->|Anonymisierung| F[(Analytics)]
    F --> G([Erkenntnisse ✨])
```

### `$ git log --graph --author=lars`

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
Okay. 🥪
```

Fun Fact: Dieses Profil ist komplett aus selbstgebauten SVG-Animationen und einer GitHub Action zusammengesetzt – schau gern in den [Quellcode](https://github.com/larsskrachen/larsskrachen).

</details>

<div align="center">
<img src="./assets/footer.svg" alt="exit 0 — danke fürs Vorbeischauen" width="100%"/>
</div>
