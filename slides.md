---
layout: cover
mdc: true
transition: fade-out
growSeed: 4
title: Effektive Code-Versionierung mit Feature-Branches
---

# Effektive Code-Versionierung mit Feature-Branches

#### Best Practices und Strategien

<!-- Icebreaker:
„Als ich das Programm der Konferenz durchgeschaut und meinen Vortrag am letzten Tag, kurz bevor für manche die Heimreise beginnt, entdeckt habe, dachte ich mir im ersten Moment: Na Super… 😅
Aber keine Sorge – obwohl das Thema eher trocken klingt, habe ich einige Bausteine herausgepickt. Mit ein paar anschaulichen Erklärungen und Tipps versuche ich, das doch etwas trockene Thema lebendig und interessant zu gestalten. -->

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

- 32 Jahre alt, aus NRW
- 9+ Jahre Erfahrung in der IT-Welt
- Team Lead & Lead Angular developer @ Eviden Germany GmbH
- Full Stack Entwickler, Schwerpunkt Frontend 
- JS/TS // Vue // React // Angular // CSS // Design
- CrossFitter/Hobby Boxer/Runner/Daddy

<div my-10 flex items-center justify-center>
  <div i-ri-user-3-line op50 ma text-xl />
  <div><a href="https://jan-friebe.de" target="_blank" class="inline border-none!">jan-friebe.de</a></div>
  <div i-ri-github-line op50 ma text-xl/>
  <div><a href="https://github.com/friebe" target="_blank" class="border-none! font-300">friebe</a></div>
  <div i-ri-twitter-x-line op50 ma text-xl/>
  <div><a href="https://twitter.com/jan_friebe" target="_blank" class="border-none! font-300">jan_friebe</a></div>
</div>
</template>

<!-- 
- 32 Jahre alt, aus einem kleinen Dörfchen von NRW nähe Münster
- seit 2009 in der IT-Welt aktiv
- Ich arbeite aktuell als Team Lead & Lead developer in 2 bilingualen Teams bei Eviden - ein atos buisness (einer der größten IT Dienstleiter Europas) für ein Produkt der Identitäts und Zugriffsverwaltung
- Durch meine Position komme ich aktuell nicht mehr so viel zur Programmierung aber ich komme ursprünglich aus der Frontend Ecke
- Hobbys sind Sport und Daddy sein
-->
---


# Fahrplan
1. Versionierung
2. Einführung in branching Strategien (Vor- und Nachteile)

**Tipps und best practises**

3. Branch Namenskonvention
4. Das approval System
5. PR Management
6. Commit Nachrichten
7. Nutzung von CI/CD
8. Tooltipps

<!--
- Zuerst kommt ein bisschen langweilige Theorie, Strategien
- Anschließend kommt der interessante Teil wo ich ein paar wichtige Bausteine vorstelle die mir in meiner Karriere über den weg gelaufen sind

-->

---
layout: cover
---

# Versionierung

### Wir versionieren Code um Änderungen nachverfolgen zu können, die Zusammenarbeit (im Team) zu erleichtern und stabile Entwicklungsprozesse mit klaren Release-Zyklen zu gewährleisten.

<!--
- Damit wir alle mit dem gleichen Grundverständis starten, hier ein Satz zur Erklärung
- Jetzt stellt sich natürlich eine offensichtliche Frage
-->

---
layout: cover
---

<h2>Wie kann ich die Vorteile einer strukturierten Versionierung optimal für mein Projekt nutzen?</h2>
<span v-click v-mark.lime.op90 inline-block p3>Mit der richtigen Strategie!</span>

<v-click at="+2">
  <span class="bg-gray-100 text-gray-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">Github Flow</span>
  <span class="bg-gray-100 text-gray-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">Git Flow</span>
</v-click>

<!--
- Wie kann ich denn die Vorteile nutzen, sodass mein Projekt übersichtlicher wird ?
- Klick
- Ja und wie so oft heißt es hier auch "it depends", aber im wesentlichen gibt es da zwei Hautstrategien
- Klick
- da im Netz viel darüber steht habe ich heute ein paar Bausteine rausgepickt anstelle den Inhalt in Gänze wiederzugeben

-->
---
layout: cover
---

## Single-Branch-Strategie - Ein branch für alles!

<span delay200="1" origin-top-left rotate-12 i-emojione-monotone:anxious-face-with-sweat w-5em h-5em absolute top-25 right-25></span>
<div v-click>
<div text-yellow2 italic>Versteht mich nicht falsch, es ist völlig in Ordnung, mit einem Zweig zu arbeiten, wenn du alleine arbeitest. Sobald du aber im Team arbeitest, reicht die Strategie meist nicht mehr aus</div>
</div>

<!--
- Zur vollständigkeithalber und zum Verständis möchte ich euch einmal die trunk based Strategie vorstellen.
- Die wird wahrscheinlich viele kennen
- Klick
- Versteht mich nicht falsch, wenn man alleine arbeitet ist das vollkommen ausreichend aber < 1 wird es schwer 
-->

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

<!--
- keine klare Trennung zwischen neuen Features
- Unfertige oder unstabiler Code kann in den Hauptcode gelangen
- Schwer nachzuvollziehen durch Code-Vermischung woher das Problem kommt
- hohe Wahrscheinlichkeit für Merge-Konflikte besonders wenn mehrere Personen parallel an unterschiedlichen Teilen des Codes arbeiten 
- gleichzeitig zu entwickeln und zu testen ist schwer
- Entwickler müssen abwarten, bis andere ihre Änderungen abgeschlossen haben, was den Entwicklungsprozess verlangsamt.
- Unfertige oder nicht getestete Features können möglicherweise zusammen mit stabilen in die Produktion gehen, was das Risiko von Fehlern im Live-System erhöht.

- Dem gegenüber steht die Strategie
-->

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

<!--
- Änderungen können unabhängig voneinander getestet und integriert werden
- Gleichzeitiges entwickeln von Features ohne sich gegenseitig zu blockieren
- Steigerung der Effizientez und Flexibilität
- Jede Änderung wird nachvollziehbar und übersichtlich festgehalten 
- Risiko von Merge-Konflikten geringer. 
- Jeder Branch ist für sich isoliert, und mögliche Konflikte werden frühzeitig und kontrolliert beim Zusammenführen der Branches erkannt.
- Bugs können in separaten Bugfix-Branches behoben werden, ohne andere Arbeiten zu stören.
- Nach der Fehlerbehebung lässt sich der Bugfix gezielt in die Produktivversion integrieren, während die Entwicklung ungestört weitergeht.
- fördert die Zusammenarbeit im Team. Entwickler können Pull-Requests erstellen, wodurch der Code von anderen Teammitgliedern überprüft werden kann. 
- Man kann andere Teammitglieder leichter um Hilfe bitten
- Verbesserung der Code-Qualität und Stärkung des Teamgefühls.
- Änderungen werden dokumentiert und lassen sich zurückverfolgen. 
- Teams können jederzeit nachvollziehen, welche Änderungen wann und von wem vorgenommen wurden, was zu besserer Transparenz und Kommunikation führt.
-->

---
layout: cover
---

# Multi-Branch Beispiele

<ul>
  <li class="fadeIn"><strong>Feature Branch</strong>: Für neue Funktionen, z.B. <code>login-page</code></li>
  <li class="fadeIn" style="animation-delay: 1s;"><strong>Bugfix Branch</strong>: Für die Behebung von Fehlern, z.B. <code>fix-login-bug</code></li>
  <li class="fadeIn" style="animation-delay: 2s;"><strong>Hotfix Branch</strong>: Dringende Korrekturen in der Produktion, z.B. <code>security-patch</code></li>
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

## Was für Änderungen enthält der branch ?
<ul>
  <li><code>branch123</code></li>
</ul>

<span v-click delay200="1" origin-top-left rotate-12 i-emojione-monotone:thumbs-down w-5em h-5em absolute top-25 right-25></span>


<!-- 
- Richtig, er ist unklar definiert und erschwert es uns auf den ersten Blick zu erkennen was sein Zweck ist
Da wir nicht alle perfekt sind und es manchmal vorkommt das wir einen schlechten Namen wählen, gibt es da was simples...click -->

---
layout: cover
---

## Branch Kategorisierung

<span class="bg-gray-100 text-gray-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">features</span>
<span class="bg-gray-100 text-green-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">bugfix</span>
<span class="bg-gray-100 text-yellow-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">release</span>
<span class="bg-gray-100 text-red-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">hotfix</span>
<span class="bg-gray-100 text-pink-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">experiment</span>
<span class="bg-gray-100 text-blue-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">username</span>
<span class="bg-gray-100 text-orange-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">docs</span>
<span class="bg-gray-100 text-violet-800 text-xs font-medium me-2 px-2.5 py-0.5 rounded">config</span>

<span v-mark.lime inline-block p3 mx--2>Kategorisierung verhilt zu mehr Struktur und Effizienz im Entwicklungsprozess</span>

<span v-click delay200="1" origin-top-left rotate-12 i-emojione-monotone:thinking-face w-5em h-5em absolute top-25 right-25></span>

<!--
- **Bessere Übersicht:**
- **Klare Trennung der Aufgaben:**
- **Automatisierte Prozesse:**
- **Vermeidung von Namenskollisionen:**

-->

---
layout: cover
---

# Branch prefix - easy

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
 Ein Verfahren bei dem Code-Änderungen über Pull-Requests zur Überprüfung vorgelegt werden, bevor sie in den Hauptbranch integriert werden. 
</div>

<!--
- Ein weiterer Baustein der imho eine sehr große Rolle spielt oder spielen sollte.
- Klick
- Eine Strategie um Code Änderungen zu überprüfen Tools helfen dabei mit PRs
- Hand hoch wer von euch PRs nutzt ?
-->

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


<!-- 

-->

---
layout: cover
---

# Semantische Commits
<div v-click>
  Commit Nachrichten die nach einem bestimmten Muster verfasst werden um den Zweck der Code-Änderung eindeutig zu kennzeichnen.
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
- Ich habe euch hier ein Beispiel mitgebracht...

- Förderung der Struktur und Erleichterung für die Automatisierung 
- Klick
- Best practise in OS-Welt
- am Ende bleibt alles eine Teamvereinbarung
-->

---
layout: cover
---

<h1>CI/CD<span ml-3 text-xl>(kontinuierliche Integration)</span></h1>


- Automatisierte Tests in jedem Branch
- Kontinuierliche Bereitstellung (CD)
- Pull-Requests und Quality Gates
- Schnelle Bereitstellungszyklen

<!--
- Tests werden automatisch beim Erstellen oder Updaten eines Branches ausgeführt.
- Nur erfolgreich getesteter Code wird automatisch in Staging- oder Produktionsumgebungen bereitgestellt.
- Das gleiche gilt auch für den mergen von PRs in den Hauptcode
- Alles ist sauber und getestet und man kann daher öfter update auspielen und ist schneller
-->

---
layout: cover
---

# Tools und Unterstützungen

<ul>
  <li class="fadeIn"><strong>Husky</strong>: Pre-Commit-Hooks, z.B. für einheitliche Commit-Nachrichten</li>
  <li class="fadeIn" style="animation-delay: 1s;"><strong>Lint-Staged</strong>: Lintet nur geänderte Dateien vor einem Commit</li>
  <li class="fadeIn" style="animation-delay: 3s;"><strong>CI/CD-Tools</strong> (z.B. Jenkins, GitLab CI, GitHub Actions): Automatisiertes Testen und Build-Prozess</li>
</ul>

<!-- 
- Husky /lint-staged sind tools die vor einem commit auf Regeln prüfen
- git hooks nutzen für Tests für den branch (für alles)
- einfaches ci/cd nutzen - kennen bestimmt einige durch netlify oder vercel von euch?
-->

---
layout: cover
---

<ul>
  <li class="fadeIn" style="animation-delay: 4s;"><strong>Semantic Release</strong>: Automatische Versionierung und Changelog-Erstellung basierend auf Commits</li>
  <li class="fadeIn" style="animation-delay: 6s;"><strong>Prettier/ESLint/biome/</strong>: Einheitliche Code-Formatierung und Qualitätsprüfung</li>
  <li class="fadeIn" style="animation-delay: 7s;"><strong>Dependabot</strong>: Automatisierte Updates von Abhängigkeiten in Branches</li>
  <li class="fadeIn" style="animation-delay: 8s;"><strong>Branch Naming Conventions Tools</strong> (z.B. Commitizen): Erzwingt konsistente Branch-Namen und Commit-Nachrichten</li>
  <li class="fadeIn" style="animation-delay: 9s;"><strong>Review Tools</strong> (z.B. SonarQube): Automatische Code-Qualitätsanalyse</li>
</ul>

<!-- 
- sofern alles sauber ist, changelogs oder sogar release notes automatisch erstellen lassen cli, npm deps.
- linten o testausführung in deiner IDE sowie später als github action
- Nutzen von Qualitätsanalysetools wie SonarQube wahlweise sogar als github action automatisch

- **Ihr seht es gibt einen Haufen an Möglichkeiten, die ihr ausprobieren könnt.**
- In diesem Sinne macht was draus. ;)
-->

---
layout: end
---

## Danke für eure Aufmerksamkeit. Fragen? <ri-heart-fill class="text-orange-500 text-xxl" />
