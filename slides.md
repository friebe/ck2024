---
layout: cover
mdc: true
transition: fade-out
growSeed: 4
title: Effektive Code-Versionierung mit Feature-Branches
---

# Effektive Code-Versionierung mit Feature-Branches

#### Best Practices und Strategien

---
growSeed: 1
layout: two-cols
layoutClass: flex items-center
---

<template class="" v-slot:default>

![](/intro.png){.w-70.h-70.mr-5.ml-20}

</template>
<template v-slot:right>

# Jan Friebe

- 32 Jahre alt
- komme aus NRW 
- Team Lead & Lead Angular developer @Eviden
- Full Stack Entwickler mit Schwerpunkt Frontend 
- JS/TS // Vue // React // Angular // CSS // Design
- CrossFitter


<div my-10 flex items-center justify-center>
  <div i-ri-user-3-line op50 ma text-xl />
  <div><a href="https://jan-friebe.de" target="_blank" class="inline border-none!">jan-friebe.de</a></div>
  <div i-ri-github-line op50 ma text-xl/>
  <div><a href="https://github.com/friebe" target="_blank" class="border-none! font-300">friebe</a></div>
  <div i-ri-twitter-x-line op50 ma text-xl/>
  <div><a href="https://twitter.com/jan_friebe" target="_blank" class="border-none! font-300">jan_friebe</a></div>
</div>
</template>
---

# Fahrplan
<h3 flex="~ col">
<div text-2xl origin-top-left transition duration-500 :class="$clicks <= 1 ? 'scale-120' : 'op50'">
  <span v-click>
    1. Versionierung?<br>
    2. Einführung in branching Strategien (Vorteile & Nachteile)<br>
  </span>
</div>
<div leading-10 mt3 forward:delay-300 v-click>
<h2 mt5 mb4>Tipps und best practises</h2>
2. Branch Namenskonvention<br>
3. Effektives Management von PRs<br>
3. Integration von CI/CD (Linting,Tests)<br>
3. Das Approval System<br>
4. Semantische commit Nachrichten<br>
6. Release Management
</div>
</h3>

---
layout: cover
---

# Versionierung?

### Wir versionieren Code, um Änderungen nachverfolgen zu können, die Zusammenarbeit (im Team) zu erleichtern und stabile Entwicklungsprozesse mit klaren Release-Zyklen zu gewährleisten.

---
layout: cover
---

<h2>Wie kann ich die Vorteile einer strukturierten Versionierung optimal für mein Projekt nutzen?</h2>
<span v-click v-mark.lime.op90 inline-block p3>Mit der richtigen Strategie!</span>

<v-click at="+2">
  <span  class="bg-gray-100 text-gray-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">Github Flow</span>
  <span class="bg-gray-100 text-gray-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">Git Flow</span>
</v-click>

---
layout: cover
---

## Single-Branch-Strategie - Ein branch für alles!

<div v-click>
<div text-yellow2 italic>Versteht mich nicht falsch, es ist völlig in Ordnung, mit einem Zweig zu arbeiten, wenn du alleine arbeitest. Sobald du aber im Team arbeitest, reicht die Strategie meist nicht mehr aus</div>
</div>

---
layout: cover
---

# Nachteile der Single-Strategie

<ri-close-fill class="text-red-600 text-xl" /> Fehlende Isolation von Features<br>
<ri-close-fill class="text-red-600 text-xl" /> Schwierige Fehlerbehebung/Lokalisierung<br>
<ri-close-fill class="text-red-600 text-xl" /> Erhöhtes Konfliktrisiko<br>
<ri-close-fill class="text-red-600 text-xl" /> Keine parallele Entwicklung<br>
<ri-close-fill class="text-red-600 text-xl" /> Kein sauberer Release-Prozess<br>

<span v-click v-mark.lime inline-block p3 mx--2>Wir büßen erheblich an Flexibilität ein!</span>

---
layout: cover
---

## Multi-Branch-Strategie - Arbeiten mit Feature branches!

---
layout: cover
---

# Vorteile der Multi-Strategie

<ri-check-fill class="text-green-600 text-xl" /> Isolation von Änderungen<br>
<ri-check-fill class="text-green-600 text-xl" /> Parallele Entwicklung<br>
<ri-check-fill class="text-green-600 text-xl" /> Saubere Versionskontrolle<br>
<ri-check-fill class="text-green-600 text-xl" /> Konfliktvermeidung<br>
<ri-check-fill class="text-green-600 text-xl" /> Bug fixing<br>
<ri-check-fill class="text-green-600 text-xl" /> Kollaboration / Zusammenarbeit<br>
<ri-check-fill class="text-green-600 text-xl" /> Bessere Rückverfolgbarkeit/Transparenz<br>

---
layout: cover
---

# Multi-Branch Beispiele

<ul>
  <li class="fadeIn"><strong>Feature Branch</strong>: Für neue Funktionen, z.B. <code>login-page</code></li>
  <li class="fadeIn" style="animation-delay: 1s;"><strong>Bugfix Branch</strong>: Für die Behebung von Fehlern, z.B. <code>fix-login-bug</code></li>
  <li class="fadeIn" style="animation-delay: 2s;"><strong>Hotfix Branch</strong>: Dringende Korrekturen in der Produktion, z.B. <code>hotfix/security-patch</code></li>
  <li class="fadeIn" style="animation-delay: 3s;"><strong>Refactoring Branch</strong>: Um Code zu verbessern, z.B. <code>user-authentication</code></li>
  <li class="fadeIn" style="animation-delay: 4s;"><strong>Documentation Branch</strong>: Für Änderungen an der Dokumentation, z.B. <code>update-api-docs</code></li>
  <li class="fadeIn" style="animation-delay: 5s;"><strong>Release Branch</strong>: Um eine Version vorzubereiten, z.B. <code>v1.0.0</code></li>
</ul>

<style>
  .fadeIn {
    opacity: 0;
    animation: fadeIn 1s forwards;
  }
  @keyframes fadeIn {
    to {
      opacity: 1;
    }
  }
</style>

<span v-click v-mark.lime inline-block p3 mx--2>Für jede Arbeit wird ein eigener, isolierte branch angelegt!</span>

---
layout: cover
---

## Kategorisiere deine branches

<span class="bg-gray-100 text-gray-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">features</span>
<span class="bg-gray-100 text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">bugfix</span>
<span class="bg-gray-100 text-yellow-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">release</span>
<span class="bg-gray-100 text-red-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">hotfix</span>
<span class="bg-gray-100 text-pink-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">experiment</span>
<span class="bg-gray-100 text-blue-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">username</span>
<span class="bg-gray-100 text-orange-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">docs</span>
<span class="bg-gray-100 text-violet-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">config</span>

<span  v-mark.lime inline-block p3 mx--2>Kategorisierung verhilt zu mehr Struktur und Effizienz im Entwicklungsprozess</span>

<span v-click delay200="1" origin-top-left rotate-12 i-emojione-monotone:thinking-face w-5em h-5em absolute top-25 right-25></span>

<!--
Bessere Übersicht: Branches sind sofort anhand ihres Namens erkennbar. Teammitglieder sehen direkt, woran gearbeitet wird (neue Features, Bugfixes, Refactorings etc.).

Klare Trennung der Aufgaben: Branches werden nach Art der Arbeit klar voneinander getrennt. So vermeidet man Verwirrung oder Konflikte bei parallelen Entwicklungen.

Effiziente Zusammenarbeit: Es wird einfacher, im Team zu arbeiten. Wenn jeder seine Branches nach einer einheitlichen Konvention benennt, können sich alle besser orientieren und Konflikte im Code minimieren.

Automatisierte Prozesse: Viele CI/CD-Tools können basierend auf Branch-Namen automatisierte Prozesse wie Tests oder Deployments ausführen, z.B. für release/-Branches.

Nachvollziehbarkeit: Im Projektverlauf kann man rückblickend besser verstehen, welche Branches für welche Aufgaben genutzt wurden, was die Wartung erleichtert.

Vermeidung von Namenskollisionen: Kategorisierte Branches verhindern, dass verschiedene Teammitglieder versehentlich Branches mit ähnlichen Namen erstellen.

-->

---
layout: cover
---

# Prefixe deine branches

<ul>
  <li class="fadeIn"><strong>Feature Branch</strong>: Für neue Funktionen, z.B. <code>feature/login-page</code></li>
  <li class="fadeIn" style="animation-delay: 1s;"><strong>Bugfix Branch</strong>: Für die Behebung von Fehlern, z.B. <code>bugfix/fix-login-bug</code></li>
  <li class="fadeIn" style="animation-delay: 2s;"><strong>Hotfix Branch</strong>: Dringende Korrekturen in der Produktion, z.B. <code>hotfix/security-patch</code></li>
  <li class="fadeIn" style="animation-delay: 3s;"><strong>Refactoring Branch</strong>: Um Code zu verbessern, z.B. <code>refactor/user-authentication</code></li>
  <li class="fadeIn" style="animation-delay: 4s;"><strong>Documentation Branch</strong>: Für Änderungen an der Dokumentation, z.B. <code>docs/update-api-docs</code></li>
  <li class="fadeIn" style="animation-delay: 5s;"><strong>Release Branch</strong>: Um eine Version vorzubereiten, z.B. <code>release/v1.0.0</code></li>
</ul>

<!--
Einfach beim branch anlegen den namen mit prefix eingeben
-->

---
layout: cover
---

# Das approval System

<div v-click>
 Ein Verfahren, bei dem Code-Änderungen über Pull-Requests zur Überprüfung vorgelegt werden, bevor sie in den Hauptbranch integriert werden. 
</div>

---
layout: cover
---

# Vorteile des approval Systems

<ri-check-fill class="text-green-600 text-xl" /> Sicherstellung von Code-Qualität<br>
<ri-check-fill class="text-green-600 text-xl" /> Früherkennung von Fehlern und Problemen<br>
<ri-check-fill class="text-green-600 text-xl" /> Förderung von Tranzparenz und Zusammenarbeit im Team<br>
<ri-check-fill class="text-green-600 text-xl" /> Gewährleistung und Einhaltung von Standards und Richtlinien

---
layout: cover
---

# Tipps für Pull Requests

1. Klare Beschreibungen und Kontextinformationen
2. Kleine, fokussierte Änderungen
3. Automatisierte Tests und Linting
4. Konstruktives Feedback geben und annehmen

---
layout: cover
---

# Semantische Commits
<div v-click>
  Commit Nachrichten die nach einem bestimmten Muster verfasst werden, um den Zweck der Code-Änderung eindeutig zu kennzeichnen.
</div>

---
layout: cover
---

# Beispiel

```bash
feat(user-authentication): Add OAuth2 login functionality
Implement OAuth2 authentication using Google Sign-In Api
- Configure OAth2 client Id and secret
- Add login button to the user
```

<div class="text-white:60 flex flex-col">
<div>type = feat</div>
<div>scope = user-authentication</div>
<div>short summary = Add OAuth2 login func</div>
<div>Longer description = Detailed description & bullet points</div>
</div>

<div v-click>
<span class="bg-gray-100 text-gray-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">feat</span>
<span class="bg-gray-100 text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">fix</span>
<span class="bg-gray-100 text-yellow-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">docs</span>
<span class="bg-gray-100 text-red-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">style</span>
<span class="bg-gray-100 text-pink-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">refactor</span>
<span class="bg-gray-100 text-blue-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">test (adding or modifying test)</span>
<span class="bg-gray-100 text-orange-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">core (other changes related to build e.g. maintenance tasks</span></div>

<!--
Förderung der Struktur und Erleichterung für die Automatisierung 
-->

---
---

# Release Management

---
layout: cover
---

# Tools und Unterstützungen

<ul>
  <li class="fadeIn"><strong>Husky</strong>: Pre-Commit-Hooks, z.B. für einheitliche Commit-Nachrichten</li>
  <li class="fadeIn" style="animation-delay: 1s;"><strong>Lint-Staged</strong>: Lintet nur geänderte Dateien vor einem Commit</li>
  <li class="fadeIn" style="animation-delay: 2s;"><strong>Git Hooks</strong>: Automatisierte Aktionen wie Formatierung und Tests vor Commit/Push</li>
  <li class="fadeIn" style="animation-delay: 3s;"><strong>CI/CD-Tools</strong> (z.B. Jenkins, GitLab CI, GitHub Actions): Automatisiertes Testen und Build-Prozess</li>
</ul>

---
layout: cover
---

<ul>
  <li class="fadeIn" style="animation-delay: 4s;"><strong>Semantic Release</strong>: Automatische Versionierung und Changelog-Erstellung basierend auf Commits</li>
  <li class="fadeIn" style="animation-delay: 5s;"><strong>Branch Protection Rules</strong> (z.B. GitHub, GitLab): Regeln für Branches festlegen (z.B. Reviews, CI-Prüfungen)</li>
  <li class="fadeIn" style="animation-delay: 6s;"><strong>Prettier/ESLint</strong>: Einheitliche Code-Formatierung und Qualitätsprüfung</li>
  <li class="fadeIn" style="animation-delay: 7s;"><strong>Dependabot</strong>: Automatisierte Updates von Abhängigkeiten in Branches</li>
  <li class="fadeIn" style="animation-delay: 8s;"><strong>Branch Naming Conventions Tools</strong> (z.B. Commitizen): Erzwingt konsistente Branch-Namen und Commit-Nachrichten</li>
  <li class="fadeIn" style="animation-delay: 9s;"><strong>Review Tools</strong> (z.B. SonarQube): Automatische Code-Qualitätsanalyse</li>
</ul>

---
layout: end
---

## Danke für eure Aufmerksamkeit <ri-heart-fill class="text-orange-500 text-xxl" />
