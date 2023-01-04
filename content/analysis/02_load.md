<h1>Webbplatsers laddningstid och användbarhet</h1>
<p>Syftet med rapporten är att undersöka laddningstider och användarbarhet över 3st separata webbsidor för att finna faktorer som kan påverka prestandan samt hitta lösningar och övriga optimerings åtgärder.</p>

<h2>Urval</h2>
<p>Mitt urval för denna gången består av 3st socialamedier platformar, vilket blev; Twitter, Reddit och Twitch. Samtliga sidor har en del foton och även videor som visas upp för användaren, vilket kan vara påfrästande för prestandand beroende på bildstorlekar eller kompremeringsgrad.</p>

<h2>Metod</h2>
<p>För att utvärdera prestandan för samtliga sidorna används verktyget pagespeed.web. Pagespeed mäter faktorer bland annat prestanda, tillgänlighet, effektivitet mm i antal procentenheter och dessa värden kommer används för att rangordna sidorn från urvalet. För att få ytterligare data och felåtgärder används nätverksfliken i webbläsarens (mitt fall Brave) inbyggda utvecklingsverktyg.</p>

<h2>Resultat</h2>
<p>Efter samtliga tester visar det att twitter är en klar vinnare både inom desktop och mobilt gränssnitt enligt den totala prestanda betyget från pagespeed.web. Twitter fick 86 poäng av möjliga 100 poäng för desktop och 65 poäng för mobil. På andra plats kom twitch med 30,3 poäng för desktop och 49 poäng för mobil. På tredje och sista plats tilldelas till reddit med 28 poäng för desktop och 16,3 poäng.</p>
<br>
<iframe width="510px" height="420px" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vQuw0Q47iQX8-8A9d7kCQ-oK3uBbkji6ewql78gz7j09ez9GwGWcqR7J1uRsbBqZR_LRmbPHmICoqpB/pubhtml?gid=0&amp;single=true&amp;widget=true&amp;headers=false"></iframe>
<i>Mätresultat för samtliga sidor med dess betyg, laddningstider, resursstorlek och resursantal.</i>

<h1>Twitter</h1>
<p>Twitter fick bäst betyg av pagespeed.web bland urvalen men däremot finns det fortfarande några punkter att åtgärda för att optimera prestandan. Första punkten handlar om ett antal oanvända JavaScript rader som tar upp extra resurser från webbläsaren, vilket orsaker ett antal extra sekunder som sidan behövs för att laddas. Lösningen är att helt enkelt förenkla koden eller fördela den inom olika moduler som laddas vid behov/interaktion. Nästa punkt handlar om en felaktigt bruk av en unload lyssnar, vilket kan förhindra webbläsarens egna optimering med att rensa oanvänd cache inför nästa besöka av sidan. Det slutligta punkten som twitter kan förbättre är att minska antalet DOM-element som innäslande div:ar, för att förminska resursladdningen.</p>
<img src="%base_url%/assets/img/twitter.png" alt="twitter" width="60%"/>
<br>
<img src="%base_url%/assets/img/twitter_load.png" alt="twitter"/>
<i>Resultat pagespeed.web.dev (desktop)</i>

<h1>Reddit</h1>
<p>Reddit fick sämst betyg bland urvalen där det störta problemet ligger kring prestandan. Det finns ett flertal punkter som pekar ut brister kring laddningen av media som bilder och videor. Den första och största åtgärden är att minska filstorlekarna på mediafiler genom kompremering som har en lätt belastning på resurser. Nästa förbättrings åtgärde är att reducera eller fördela JavaScript kod i separata moduler. Fonterna och övriga grafiskresurser bör även cache:as i en längre livslängd för att minska antalet omladdningar. Slutligen bör reddit applikationen minska antalet dom-element för att ytterligare minska trafiken och övriga resursförbrukningar.</p>
<img src="%base_url%/assets/img/reddit.png" alt="reddit" width="60%"/>
<br>
<img src="%base_url%/assets/img/reddit_load.png" alt="twitter"/>
<i>Resultat pagespeed.web.dev (desktop)</i>

<h1>Twitch</h1>
<p>Twitch hamnade på en andraplats av urvalen. Twitch delar en del av problemen som Reddit har, vilket är en krävande resursförbrukning av form av media. Dock skiljer sig mediatypen där twitch har primärt live-videor vilket kan göra det svårt att komprimera i real-tid då även sändaren kan kontrollera kvaliten av videon inom bestämd gränns. Självaste nättrafiken är även mer ansträngande då klienterna kräver en direkt uppkoppling för att följa videoflödet i realtid och cacher endast i ett få interval av sekunder. Det som kunna förbättras är väl livslängden av cache:erna genom att det förlängd. Dock eftersom allt sker i realtid blir det svårt att göra större förändingar inom prestandan då det betydelsefulla förändringarna är på server-sidan.</p>
<img src="%base_url%/assets/img/twitch.png" alt="twitch" width="60%"/>
<br>
<img src="%base_url%/assets/img/twitch_load.png" alt="twitter"/>
<i>Resultat pagespeed.web.dev (mobile)</i>

<h1>Analys</h1>
<p>Det jag kan dra samman är att filstorlekerna och resursantelet har en betydande effekt på självaste prestandan. Vilket tyder även på då rangordningen av sidorna från urvalet. Twitter som hade högst betyg hade få påpeklser angående laddningen av resurer. Då går även att läsa från mätningstabellen av resultatet där twitter hade snabbast laddningstid och även minst antal resursstorlek/resursantal. Medans Reddit som fick lägst betyg hade störrsta filstorlekarna och flest antal resurser. Det finns helt enkelt en tydlig förhållande mellan filstorkler och dess antal för prestandan, vilket stämmer in på urvalets vinnare; Twitter! En övrig aspekt som varje sida fick utpekad är ett antal oanvänd JavaScript kod där lösningen blev att förkorta eller separera en eller flera stycken till flera separata filer.</p>
<p>Det som anses vara en rimlig laddningstid för en sida beror på sidans huvudsakliga syfte. Dock bör man alltid ha prestanda och användbarhet i åtanke vid utvecklings av kommersiell tjänst. Om jag skulle definiera en konkret tid bör jag även specifiera en kategori av en webbplats. Om det skulle ex handla om en webbshopp eller en nyhetssida vill jag nog att innehållet laddas inom 2-3 sekunder med förutsättningarna att min internet uppkoppling är bra. Innehåll från det nämda sidorna är statiska vilket går smidigt att optimera enligt moderna bild/video kompremeringar. Då webbshoppar och nyhetssidor huvudsakliga syfte är att fånga kunderas intressen är det viktigt att det sker inom en rimlig tidsspan så att personen inte tappar sitt intresse och går till en konkurant. Medans en god optimerad webbsida ger ett gott intryck och god harmoni.</p>

<h2>Referenser</h2>
<ul>
  <li><a href="https://twitter.com/explore">Twitter</a></li>
  <li><a href="https://reddit.com/">Reddit</a></li>
  <li><a href="https://twitch.tv/">Twitch</a></li>
  <li><a href="https://pagespeed.web.dev">Pagespeed</a></li>
</ul>  

<h2>Övrigt</h2>
<p>Denna rapport är skriven av Gustaf Sundqvist.</p>