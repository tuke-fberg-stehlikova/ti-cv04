# cv04: PHP základy

Stránka týždňa s teóriou a ukážkami: https://beata.stehlikova.website.tuke.sk/ti/05.html

## Odovzdávaš

V repository *cv04* na GitHub a vo svojom webovom priestore na sigma (`ti/cv04`):

- `index.php`, `routes.php`, `form.php`, `contact.php` (po 5 riadkov), `template.php`, priečinok `content/` s `home.php`, `routes.php`, `register.php`, `contact.php`,
- cvičné súbory `variables.php`, `arrays.php`, `loops.php`,
- `css/style.css` a `img/` z minulého týždňa; staré `index.html` a `form.html` sú zmazané.

## Hodnotenie

1 bod. Web je prerobený na template so štyrmi stránkami a tri cvičné súbory sú hotové. Commit a push najneskôr do nasledujúceho cvičenia. Po každom push sa spustia automatické testy; výsledok nájdeš podľa návodu [04 Odovzdávanie](https://beata.stehlikova.website.tuke.sk/navody/04-odovzdavanie.html), časť 6.

## Prompty pre AI

Na miestach `// DOPLŇ` dopĺňaš sám.

### Ukážka 7: prompt na premenné a výpočty

```text
Vytvor PHP súbor variables.php pre web na tému [DOPLŇ tému svojho projektu].
PHP 8.1, bez databázy, bez formulára, bez JavaScriptu.

Hore v súbore v bloku <?php ... ?> vytvor šesť premenných s názvami po anglicky:
- dve typu string, jednu typu int, jednu typu float, jednu typu bool,
  jednu s rokom (int), všetko z mojej témy; hodnoty nechaj zatiaľ ukážkové,
- jeden výpočet z roku a dnešného dátumu cez date('Y'),
- jeden výpočet z float hodnôt s round na 1 desatinné miesto.

Pod tým HTML5 stránka: meta charset utf-8, meta viewport, Bootstrap 5.3 z CDN,
body s triedou container, nadpis h1 a aspoň tri odseky, v ktorých sú hodnoty
premenných dosadené cez <?= ?>. Jeden odsek má zalomenie riadku <br>.
Desatinné číslo vypíš cez number_format so slovenskou desatinnou čiarkou.

Ku každej premennej napíš komentár, aký má typ a prečo. Dve premenné nechaj
s hodnotou a komentárom // DOPLŇ: sem dáš svoju hodnotu.
```

### Ukážka 8: prompt na array a zoznam

```text
Vytvor PHP súbor arrays.php pre web na tému [DOPLŇ tému]. PHP 8.1, HTML5
s meta charset utf-8, meta viewport, Bootstrap 5.3 z CDN, body s triedou container.

V bloku <?php ... ?> hore:
- obyčajné pole $items s piatimi hodnotami typu string z mojej témy,
- asociatívne pole $item s kľúčmi name, order (int), category (string),
  price (float) a available (bool), hodnoty z mojej témy,
- pole $numbers s hodnotami [10, 2, 7, 33, 4] a jeho zoradenú kópiu cez sort.

V HTML:
- nadpis h2 a nečíslovaný zoznam <ul>, ktorý vypíše $items cez foreach
  v zápise s dvojbodkou (foreach: ... endforeach),
- odsek s počtom prvkov cez count a vetu z prvkov cez implode,
- druhý zoznam, ktorý vypíše $item ako „kľúč: hodnota" cez foreach s $key => $value,
- odsek so zoradenými $numbers cez implode.

Nechaj jeden komentár // DOPLŇ: pridaj do $items šiesty prvok cez $items[] = ...
a druhý // DOPLŇ: vypíš prvý a posledný prvok $items.
Ku každému bloku krátky slovenský komentár, čo robí.
```

### Ukážka 9: prompt na cykly

```text
Vytvor PHP súbor loops.php pre web na tému [DOPLŇ tému]. PHP 8.1, HTML5
s meta charset utf-8, meta viewport, Bootstrap 5.3 z CDN, body s triedou container.

- tabuľka s triedou table: cyklus for s počítadlom od 1 do 10, v každom riadku
  počítadlo a jeden výpočet z neho (napr. cena × počet); párne riadky majú
  triedu table-light cez $i % 2,
- číslovaný zoznam <ol> z poľa piatich hodnôt z mojej témy cez foreach
  s $i => $value, kde vypíšeš poradie od 1 a hodnotu,
- cyklus while, ktorý odpočítava od 5 do 1.

Všetky cykly v zápise s dvojbodkou (endfor, endforeach, endwhile).
Nechaj komentár // DOPLŇ: prepíš cyklus for tak, aby išiel od 10 do 1
s krokom 1 dole, a druhý // DOPLŇ: zmeň while tak, aby odpočítaval po 2.
```

### Ukážka 10: prompt na template

```text
Posielam ti svoje súbory index.html a form.html z webu na tému [DOPLŇ tému].
Rozdeľ ich na PHP šablónu a obsah. PHP 8.1. Texty, triedy Bootstrap, obrázky
a formulár nemeň. Z index.html vzniknú dve stránky: Domov (všetko okrem
[DOPLŇ názov sekcie s položkami, napr. ciest]) a [DOPLŇ názov stránky, napr. Cesty]
(sekcie s kartami a tabuľkou).

Vytvor presne tieto súbory:
- template.php: celý rám stránky: <!doctype html>, <head> s meta charset,
  meta viewport, <title><?= $title ?> | [DOPLŇ názov webu]</title>, Bootstrap CSS
  a css/style.css; navbar z môjho index.html s položkami Domov (index.php),
  [DOPLŇ, napr. Cesty] (routes.php) a Registrácia (form.php), kde trieda active
  sa dáva podmienkou <?= $active == 'index' ? 'active' : '' ?> (s hodnotami
  'index', 'routes', 'form'); <main class="container"> s <h1><?= $title ?></h1>
  a riadkom <?php include $content; ?>; pätička s rokom cez date('Y');
  Bootstrap JS pred </body>.
- content/home.php: z <main> môjho index.html všetky sekcie okrem sekcie
  s kartami a tabuľkou; bez <html>, <head>, menu a pätičky, bez h1.
- content/routes.php: z <main> môjho index.html iba sekcie s kartami a tabuľkou.
- content/register.php: iba formulár z môjho form.html, bez všetkého ostatného.
- index.php: päť riadkov: <?php, $title = 'Domov', $active = 'index',
  $content = 'content/home.php', include 'template.php'.
- routes.php a form.php: to isté s hodnotami pre cesty a pre registráciu.

Do template.php napíš komentár // DOPLŇ: pridaj štvrtú položku menu Kontakt
na contact.php. Ku každému súboru krátky komentár, čo v ňom je a čo v ňom nie je.

Tu sú moje súbory:
[VLOŽ index.html a form.html]
```

## Úlohy

**Úloha 5.1: Príprava Kubeflow.** Priprav si Kubeflow podľa návodu [04 Odovzdávanie](https://beata.stehlikova.website.tuke.sk/navody/04-odovzdavanie.html), časť 1: v Explorer je hore WEB, dole na stavovej lište je **Go Live**. Ak tam nie je, rozšírenia vráti tento príkaz v termináli:

```bash
code-server --install-extension Natizyskunk.sftp --install-extension yandeu.five-server --install-extension bmewburn.vscode-intelephense-client --install-extension mblode.twig-language-2
```

Potom `F1`, **Developer: Reload Window**. Nastavenie pripojenia na sigma zostáva.

**Úloha 5.2: Zadanie a kópia minulého týždňa.** Prijmi zadanie *cv04* v Classroom 50 (link je vyššie) a repository naklonuj do `~/web/ti/cv04` podľa návodu 04, časti 2 a 3. Potom do neho prekopíruj svoj web z minulého týždňa:

```bash
cd ~/web/ti
rsync -a --exclude .git --exclude .github --exclude README.md cv03/ cv04/
ls cv04
```

**Úloha 5.3: Prvý PHP výpis.** Vytvor `variables.php` podľa Ukážky 1 so svojimi hodnotami: tri premenné rôznych typov a jeden výpočet, výpis cez `echo` spojený bodkou. Ulož a otvor `https://sigma.tuke.sk/student/meno.priezvisko/ti/cv04/variables.php`. Všetko je v jednom riadku.

**Úloha 5.4: Premenné s HTML.** Prompt z Ukážky 7 vlož do AI, výsledok ulož ako `variables.php` (prepíše úlohu 5.3). Doplň miesta `// DOPLŇ`. Ulož, F5: nadpis, odseky, zalomenie. `Ctrl` + `U`: v zdroji nie je PHP.

**Úloha 5.5: Typy.** Do `variables.php` pridaj `var_dump` všetkých premenných a over, že každá má typ, ktorý si chcel. Jednu premennú zmeň na zlý typ (číslo v apostrofoch), pozri, čo `var_dump` ukáže, a vráť to.

**Úloha 5.6: Polia.** Prompt z Ukážky 8, výsledok ulož ako `arrays.php`. Doplň `// DOPLŇ`: pridaj šiesty prvok, vypíš prvý a posledný. Over v prehliadači, že zoznam má šesť položiek a `count` sedí.

**Úloha 5.7: Zoradenie.** Do `arrays.php` pridaj pole troch čísel zo svojej témy ako `int` a to isté ako `string`, obe zoraď cez `sort` a vypíš. Do komentára napíš jednou vetou, prečo sú výsledky rôzne.

**Úloha 5.8: Cykly.** Prompt z Ukážky 9, výsledok ulož ako `loops.php`. Doplň `// DOPLŇ`: prepíš `for` od 10 do 1, `while` po 2.

**Úloha 5.9: Template.** Prompt z Ukážky 10 so svojimi `index.html` a `form.html`. Ak tvoj `index.html` má len sekciu s cestami, dopíš do `content/home.php` sám krátku sekciu O stene s jedným odsekom. Výsledné súbory ulož presne pod tými názvami (priečinok `content/` vytvor: pravý klik na `cv04`, **New Folder…**). Staré `index.html` a `form.html` zmaž (pravý klik na súbor, **Delete**). Otvor `index.php`, `routes.php` aj `form.php` na sigma: texty sú z cv03 a `active` je pri správnej položke.

**Úloha 5.10: Stránka Kontakt.** Ručne, bez AI: skopíruj `index.php` ako `contact.php` a zmeň tri hodnoty; vytvor `content/contact.php` s nadpisom `h2`, odsekom a kontaktom (nie skutočným telefónom); doplň položku Kontakt do menu v `template.php` aj s podmienkou pre `active`.

**Úloha 5.11: Chyba naschvál.** V `contact.php` zmaž bodkočiarku, ulož, F5, prečítaj hlásenie a nájdi číslo riadka. Oprav. Potom v `template.php` prepíš `$title` na `$titel`, pozri hlásenie, oprav.

**Úloha 5.12: Commit a push.** Podľa návodu [04 Odovzdávanie](https://beata.stehlikova.website.tuke.sk/navody/04-odovzdavanie.html), časť 5; commit po každej hotovej úlohe. Výsledok testov podľa časti 6.

**Úloha 5.13: Upload Folder a kontrola na sigma.** Podľa návodu 04, časť 7: pravý klik na `cv04`, v menu úplne dole **Upload Folder**. Over všetky stránky: `index.php`, `routes.php`, `form.php`, `contact.php`, `variables.php`, `arrays.php`, `loops.php`.

**Hodnotenie:** 1 bod. V repository *cv04* na GitHub aj na sigma je web prerobený na template so štyrmi stránkami a tri cvičné súbory `variables.php`, `arrays.php`, `loops.php`. Commit a push najneskôr do nasledujúceho cvičenia.

---

# cv04: PHP basics

The week page with theory and examples: https://beata.stehlikova.website.tuke.sk/ti/05.html

## What you submit

In the repository *cv04* on GitHub and in your web space on sigma (`ti/cv04`):

- `index.php`, `routes.php`, `form.php`, `contact.php` (5 lines each), `template.php`, the `content/` folder with `home.php`, `routes.php`, `register.php`, `contact.php`,
- the practice files `variables.php`, `arrays.php`, `loops.php`,
- `css/style.css` and `img/` from last week; the old `index.html` and `form.html` are deleted.

## Grading

1 point. The website is rebuilt with a template and four pages, and the three practice files are done. Commit and push by the next lab at the latest. Automatic tests run after every push; find the result following guide [04 Submitting](https://beata.stehlikova.website.tuke.sk/navody/04-odovzdavanie.html), part 6.

## AI prompts

You fill in the `// DOPLŇ` places yourself.

### Example 7: a prompt for variables and calculations

```text
Create a PHP file variables.php for a website about [FILL IN your project topic].
PHP 8.1, no database, no form, no JavaScript.

At the top of the file, in a <?php ... ?> block, create six variables with
English names:
- two of type string, one int, one float, one bool, one with a year (int),
  all from my topic; leave sample values for now,
- one calculation from the year and today's date via date('Y'),
- one calculation from the float values with round to 1 decimal place.

Below it an HTML5 page: meta charset utf-8, meta viewport, Bootstrap 5.3 from
the CDN, body with the class container, an h1 heading and at least three
paragraphs in which the variable values are inserted with <?= ?>. One paragraph
has a line break <br>. Print the decimal number with number_format using a
decimal comma.

Add a comment to every variable saying its type and why. Leave two variables
with a value and the comment // DOPLŇ: put your own value here.
```

### Example 8: a prompt for an array and a list

```text
Create a PHP file arrays.php for a website about [FILL IN the topic]. PHP 8.1,
HTML5 with meta charset utf-8, meta viewport, Bootstrap 5.3 from the CDN,
body with the class container.

In a <?php ... ?> block at the top:
- a plain array $items with five string values from my topic,
- an associative array $item with the keys name, order (int), category (string),
  price (float) and available (bool), values from my topic,
- an array $numbers with the values [10, 2, 7, 33, 4] and its sorted copy via sort.

In the HTML:
- an h2 heading and an unordered list <ul> that prints $items with foreach
  in the colon notation (foreach: ... endforeach),
- a paragraph with the number of elements via count and a sentence made of
  the elements via implode,
- a second list that prints $item as "key: value" with foreach and $key => $value,
- a paragraph with the sorted $numbers via implode.

Leave one comment // DOPLŇ: add a sixth element to $items with $items[] = ...
and another // DOPLŇ: print the first and the last element of $items.
Add a short comment to every block saying what it does.
```

### Example 9: a prompt for loops

```text
Create a PHP file loops.php for a website about [FILL IN the topic]. PHP 8.1,
HTML5 with meta charset utf-8, meta viewport, Bootstrap 5.3 from the CDN,
body with the class container.

- a table with the class table: a for loop with a counter from 1 to 10, in
  every row the counter and one calculation from it (e.g. price × quantity);
  even rows get the class table-light via $i % 2,
- an ordered list <ol> from an array of five values from my topic via foreach
  with $i => $value, printing the order from 1 and the value,
- a while loop that counts down from 5 to 1.

All loops in the colon notation (endfor, endforeach, endwhile).
Leave a comment // DOPLŇ: rewrite the for loop to go from 10 down to 1 in
steps of 1, and another // DOPLŇ: change the while loop to count down by 2.
```

### Example 10: a prompt for the template

```text
I am sending you my files index.html and form.html from a website about
[FILL IN the topic]. Split them into a PHP template and content. PHP 8.1.
Do not change the texts, the Bootstrap classes, the images or the form.
index.html becomes two pages: Home (everything except [FILL IN the name of
the section with the items, e.g. routes]) and [FILL IN the page name, e.g. Routes]
(the sections with the cards and the table).

Create exactly these files:
- template.php: the whole page frame: <!doctype html>, <head> with meta charset,
  meta viewport, <title><?= $title ?> | [FILL IN the site name]</title>, the
  Bootstrap CSS and css/style.css; the navbar from my index.html with the items
  Home (index.php), [FILL IN, e.g. Routes] (routes.php) and Registration (form.php),
  where the active class is given by the condition
  <?= $active == 'index' ? 'active' : '' ?> (with the values 'index', 'routes',
  'form'); <main class="container"> with <h1><?= $title ?></h1> and the line
  <?php include $content; ?>; a footer with the year via date('Y');
  the Bootstrap JS before </body>.
- content/home.php: from the <main> of my index.html all sections except the one
  with the cards and the table; without <html>, <head>, menu and footer, without h1.
- content/routes.php: from the <main> of my index.html only the sections with
  the cards and the table.
- content/register.php: only the form from my form.html, without everything else.
- index.php: five lines: <?php, $title = 'Home', $active = 'index',
  $content = 'content/home.php', include 'template.php'.
- routes.php and form.php: the same with the values for routes and for registration.

In template.php write the comment // DOPLŇ: add a fourth menu item Contact
leading to contact.php. Add a short comment to every file saying what is in it
and what is not.

Here are my files:
[PASTE index.html and form.html]
```

## Tasks

**Task 5.1: Getting Kubeflow ready.** Get Kubeflow ready following guide [04 Submitting](https://beata.stehlikova.website.tuke.sk/navody/04-odovzdavanie.html), part 1: Explorer shows WEB at the top, the status bar at the bottom shows **Go Live**. If it does not, this terminal command brings the extensions back:

```bash
code-server --install-extension Natizyskunk.sftp --install-extension yandeu.five-server --install-extension bmewburn.vscode-intelephense-client --install-extension mblode.twig-language-2
```

Then `F1`, **Developer: Reload Window**. The sigma connection settings stay.

**Task 5.2: The assignment and a copy of last week.** Accept the assignment *cv04* in Classroom 50 (the link is above) and clone the repository into `~/web/ti/cv04` following guide 04, parts 2 and 3. Then copy your website from last week into it:

```bash
cd ~/web/ti
rsync -a --exclude .git --exclude .github --exclude README.md cv03/ cv04/
ls cv04
```

**Task 5.3: The first PHP output.** Create `variables.php` following Example 1 with your own values: three variables of different types and one calculation, printed with `echo` joined with dots. Save and open `https://sigma.tuke.sk/student/name.surname/ti/cv04/variables.php`. Everything is on one line.

**Task 5.4: Variables with HTML.** Paste the prompt from Example 7 into an AI and save the result as `variables.php` (it replaces task 5.3). Fill in the `// DOPLŇ` places. Save, F5: a heading, paragraphs, a line break. `Ctrl` + `U`: no PHP in the source.

**Task 5.5: Types.** Add a `var_dump` of all variables to `variables.php` and check that each has the type you wanted. Change one variable to a wrong type (a number in quotes), see what `var_dump` shows, and change it back.

**Task 5.6: Arrays.** The prompt from Example 8; save the result as `arrays.php`. Fill in `// DOPLŇ`: add a sixth element, print the first and the last. Check in the browser that the list has six items and `count` matches.

**Task 5.7: Sorting.** Add to `arrays.php` an array of three numbers from your topic as `int` and the same as `string`, sort both with `sort` and print them. Write in a comment, in one sentence, why the results differ.

**Task 5.8: Loops.** The prompt from Example 9; save the result as `loops.php`. Fill in `// DOPLŇ`: rewrite `for` from 10 down to 1, `while` by 2.

**Task 5.9: Template.** The prompt from Example 10 with your own `index.html` and `form.html`. If your `index.html` has only the section with the routes, write a short About section with one paragraph into `content/home.php` yourself. Save the resulting files exactly under those names (create the `content/` folder: right-click `cv04`, **New Folder…**). Delete the old `index.html` and `form.html` (right-click the file, **Delete**). Open `index.php`, `routes.php` and `form.php` on sigma: the texts are from cv03 and `active` is on the right item.

**Task 5.10: The Contact page.** By hand, without AI: copy `index.php` as `contact.php` and change the three values; create `content/contact.php` with an `h2` heading, a paragraph and a contact (not a real phone number); add the Contact item to the menu in `template.php` including the condition for `active`.

**Task 5.11: An error on purpose.** In `contact.php` delete a semicolon, save, F5, read the message and find the line number. Fix it. Then in `template.php` change `$title` to `$titel`, look at the message, fix it.

**Task 5.12: Commit and push.** Following guide [04 Submitting](https://beata.stehlikova.website.tuke.sk/navody/04-odovzdavanie.html), part 5; a commit after every finished task. The test result following part 6.

**Task 5.13: Upload Folder and the check on sigma.** Following guide 04, part 7: right-click `cv04`, **Upload Folder** at the very bottom of the menu. Check all pages: `index.php`, `routes.php`, `form.php`, `contact.php`, `variables.php`, `arrays.php`, `loops.php`.

**Grading:** 1 point. The repository *cv04* on GitHub and on sigma contains the website rebuilt with a template and four pages, and the three practice files `variables.php`, `arrays.php`, `loops.php`. Commit and push by the next lab at the latest.
