# Statistik-Projekt-Nicole
 individuelle Projektarbeit Statistik 2
# Vorhersage der Einzeleintritte bei der Bergbahn Sattel Hochstuckli

## Kurzbeschreibung

Dieses Projekt untersucht, wie zuverlässig ein Prognoseprogramm die Anzahl der Einzeleintritte bei der Bergbahn Sattel Hochstuckli vorhersagt. Dazu werden die prognostizierten Werte mit den tatsächlich gezählten Einzeleintritten verglichen.

Im Zentrum steht die Frage, ob die Vorhersage systematisch von der Realität abweicht. Die Analyse kombiniert einen Hypothesentest mit Regressionsmodellen (OLS und GLM) und ordnet das Projekt damit thematisch in die Vorlesung ein.

## Fragestellung

Die Arbeit geht von folgenden Fragen aus:

1. Unterscheidet sich die vorhergesagte Anzahl Einzeleintritte systematisch von der tatsächlich beobachteten Anzahl?
2. Wie gross sind die Abweichungen im Durchschnitt, und streuen sie stark?
3. Welche Faktoren erklären die Abweichungen, zum Beispiel Wochentag, Ferien, Feiertage, Wetter oder Saison?
4. Eignet sich ein GLM für Zähldaten besser als ein klassisches OLS-Modell?

## Hypothesen

Für den Hypothesentest wird die Differenz zwischen Vorhersage und tatsächlichem Wert betrachtet:

- **Nullhypothese \(H_0\):** Der mittlere Unterschied zwischen Prognose und tatsächlichem Wert ist null. Die Vorhersage ist also im Mittel unverzerrt.
- **Alternativhypothese \(H_1\):** Der mittlere Unterschied ist ungleich null. Die Vorhersage weicht systematisch vom tatsächlichen Wert ab.

Je nach Verteilung der Differenzen wird ein gepaarter t-Test oder ein Wilcoxon-Vorzeichen-Rang-Test verwendet. Zusätzlich werden Bias, MAE und RMSE berechnet, um die Prognosegüte zu beschreiben.

## Daten

Der Datensatz enthält pro Tag mindestens folgende Variablen:

| Variable | Beschreibung |
|---|---|
| `datum` | Tag der Beobachtung |
| `prognose` | Vom Programm vorhergesagte Anzahl Einzeleintritte |
| `ist` | Tatsächlich gezählte Anzahl Einzeleintritte |
| `differenz` | Differenz zwischen Prognose und IST |
| `wochentag` | Wochentag |
| `ferien` | Ferienzeit ja/nein |
| `feiertag` | Feiertag ja/nein |
| `wetter` | Wetterkategorie oder Wetterindikator |
| `saison` | Saison oder Monat |

Die Daten stammen aus dem Prognoseprogramm der Bergbahn sowie aus den tatsächlichen Zählungen.

## Methoden

Die Analyse erfolgt in drei Schritten:

1. **Deskriptive Auswertung:** Vergleich von Prognose und IST, Berechnung von Bias, MAE und RMSE sowie grafische Darstellung der Zeitreihen und Differenzen.
2. **Hypothesentest:** Prüfung, ob die mittlere Differenz signifikant von null abweicht. Vor dem Test wird geprüft, ob die Differenzen normalverteilt sind.
3. **Regressionsmodelle:**
   - **OLS:** Die Differenz oder der tatsächliche Wert wird durch Wochentag, Ferien, Feiertage, Wetter und Saison erklärt.
   - **GLM:** Da es sich bei den Einzeleintritten um Zähldaten handelt, wird ein Poisson- oder Negativ-Binomial-Modell geschätzt. Eine Überdispersion wird geprüft und bei Bedarf durch ein Negativ-Binomial-Modell berücksichtigt.

Die Modelle werden anhand von Residualdiagnostik, Signifikanz der Koeffizienten und Modellgüte verglichen.

## Ergebnisse

Die zentralen Ergebnisse werden hier nach Abschluss der Analyse ergänzt:

- Mittlere Differenz zwischen Prognose und IST
- p-Wert des Hypothesentests und Interpretation
- MAE und RMSE der Prognose
- Signifikante Einflussfaktoren im OLS-Modell
- Vergleich zwischen Poisson-, Negativ-Binomial- und OLS-Modell

## Limitationen

Die Analyse ist beobachtend. Wetter, kurzfristige Events, Ausfälle von Anlagen oder Änderungen am Prognoseprogramm können die tatsächlichen Einzeleintritte beeinflussen und die Ergebnisse verzerren. Zudem hängt die Aussagekraft davon ab, wie vollständig und konsistent die Prognose- und Zähldaten vorliegen.

## Kontext

Das Projekt entsteht im Rahmen des Moduls Statistik 2 an der Hochschule Luzern. Es ist thematisch in den Bereichen Hypothesentest, OLS und GLM verankert.

## Autorinnen und Autoren

- Nicole Briggen
- Projektpartner: Curdin Derungs
