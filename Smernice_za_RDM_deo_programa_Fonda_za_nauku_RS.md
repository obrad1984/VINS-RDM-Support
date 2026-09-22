# **Smernice za sekciju o upravljanju podacima (za Institut za nuklearne nauke “Vinča”)**

## (F1a Project Description Part A \- 1.2 Methodology)

*Ovo su smernice bibliotekara Instituta “Vinča” koje treba da posluže kao pomoć prilikom pisanja dela* Research Data Management *iz dokumenta* Project Description Part A (F1a) *projektne prijave.*   
*Upravljanje podacima zavisi od vrste istraživanja, tipova podataka, metodologije istraživanja i brojnih drugih faktora te je stoga gotovo nemoguće napraviti obrazac teksta koji bi mogao da posluži kao matrica za sve slučajeve.* 

*U delovima* “Primer teksta” *su dati neki primeri rečenica koje možete iskoristiti pod uslovom da ih uklopite u svoj narativ. Ovo su samo kratki primeri sa izmišljenim scenarijom u kojem projekat ima tri tipa rezultata: dva skupa podataka (jedan koji je generisan u okviru samog istraživanja i drugi koji već postoji i “pozajmljuje” se za ovaj projekat) i računarski kod koji je neophodan za manipulaciju i rad samih podataka. Vaši primeri mogu biti iscrpniji u detaljima.*

*Koristite ove smernice pre svega kako biste razumeli šta se u ovom delu prijave od vas traži, a za sva pitanja možete se uvek obratiti za savet bibliotekarima na [biblioteka@vin.bg.ac.rs](mailto:biblioteka@vin.bg.ac.rs) ili [obrad.vuckovac@vin.bg.ac.rs](mailto:obrad.vuckovac@vin.bg.ac.rs).*

## **Početna napomena: čemu ova sekcija zapravo služi**

Ovaj deo projektne dokumentacije nije DMP. Poziv traži kratku izjavu o upravljanju podacima u skladu sa [**FAIR principima**](https://www.go-fair.org/fair-principles/) ugrađenu u narativ Metodologije, dok pravi DMP dolazi kasnije kao poseban rezultat u prvih šest meseci projekta i sadrži mnogo detaljniji opis upravljanja podacima nego što se traži u ovom delu prijave. 

U praktičnom smislu, FAIR principi znače da su podaci organizovani dovoljno dobro da ih neka druga osoba — ili kompjuterski algoritam — može pronaći, pristupiti im i otvoriti ih, razumeti šta sadrže (bez potrebe da se kontaktira vlasnik), i ponovo ih upotrebiti uz jasno naznačene uslove korišćenja. Ovo poslednje je sve važnije za reproducibilnost istraživanja, ali i za AI i mašinsko učenje: skup podataka deponovan u repozitorijum sa urednim metapodacima, standardnim formatom i jasnim uslovima ponovne upotrebe direktno je upotrebljiv kao trening ili validacioni skup ili za nezavisnu verifikaciju rezultata. 

Recenzenti ovde proveravaju dve stvari: da li podnosilac razume šta FAIR znači za njegove konkretne podatke, i da li su preuzete obaveze realne za upravljanje podacima, tako da mogu da izdrže tok projekta. Šta god da se napiše ovde, trebalo bi da bude nešto što tim zaista može da ispuni, jer će DMP nakon šest meseci biti proveravan u odnosu na to.

## **Prvo rešiti izbor repozitorijuma**

Izbor repozitorijuma utiče na sva četiri FAIR principa, pa ovo treba rešiti sa učesnicima na projektu pre pisanja bilo kog od ta dva odgovora.   

**Repozitorijumi** su specijalizovani informacioni sistemi namenjeni dugoročnom čuvanju, opisivanju i omogućavanju pristupa istraživačkim podacima, softveru i drugim rezultatima istraživanja. Za razliku od mrežnog diska ili lokalnog računara, repozitorijum garantuje stabilnost, kontinuitet i infrastrukturu potrebnu da podaci ostanu dostupni i razumljivi godinama nakon završetka projekta. Njihova uloga u upravljanju podacima je centralna: oni preuzimaju odgovornost za čuvanje podataka nakon što istraživač završi aktivan rad na projektu, obezbeđuju da svaki zapis ima svoj trajni identifikator (PID) poput DOI-ja ili Handle-a, i standardizuju način na koji se podaci opisuju kroz metapodatke, čime postaju vidljivi i pronalažljivi kako za ljude, tako i za mašine. Upravo izbor repozitorijuma direktno određuje koliko će podaci zaista biti FAIR-spremni: repozitorijum koji dodeljuje PID, koristi prepoznatljiv standard za metapodatke, omogućava izvoz metapodataka (npr. putem OAI-PMH ili REST API-ja), i podržava mašinski čitljive licence u velikom delu ispunjava sve četiri FAIR komponente sam po sebi, dok skladištenje podataka van repozitorijuma, makar podaci bili tehnički "dostupni" na zahtev, obično ne zadovoljava nijednu od njih na zadovoljavajući način. [*Platforma za otvorenu nauku 2.0*](https://nitra.gov.rs/images/nauka/TONuS-Platforma_2.0-Final.pdf) Ministarstva nauke, tehnološkog razvoja i inovacija Republike Srbije izričito traži deponovanje i čuvanje podataka u proverenim repozitorijuma i u skladu sa FAIR principima.

Pri izboru repozitorijuma vodite se navikama svoje ciljane publike. Preporuka je da sledite sledeću logiku:

1. **Prepoznati disciplinski (ili tematski) repozitorijum**, ukoliko postoji za dati tip podataka (npr. PDB ili EMDB za strukturnu biologiju, Materials Cloud ili NOMAD za podatke iz nauke o materijalima, GenBank/ENA za sekvence). Recenzenti iz relevantne oblasti će ih prepoznati, a ovo povećava šansu da podaci zaista budu ponovo upotrebljeni od strane onih kojima bi bili korisni.  
2. **VinaR** (repozitorijum Instituta “Vinča”) — [https://vinar.vin.bg.ac.rs/](https://vinar.vin.bg.ac.rs/) —, kada ne postoji odgovarajući disciplinski repozitorijum, ili kao sekundarno deponovanje uz disciplinski repozitorijum radi institucionalne vidljivosti i efikasnijeg praćenja rezultata.  
3. **Opšti repozitorijum** (Zenodo, OSF, Figshare) — čest slučaj za mešovite rezultate, softver, ili skupove podataka premale ili preheterogene za disciplinski arhiv.

Koji god da se izabere, mora zaista da ispunjava FAIR zahteve, a ne samo da čuva fajlove. Deljeni mrežni disk (Google Drive, Dropbox i sl.) ili institucionalni vebsajt sa linkom za preuzimanje **nije repozitorijum u ovom smislu.**

## **1\. Tipovi podataka/istraživačkih rezultata i procenjena veličina**

**Šta se pita:** navesti tipove podataka (merenja, slike, spektri, sekvence, kod, modeli), okvirnu zapreminu, i da li se bilo šta od toga oslanja na postojeće/ponovo upotrebljene podatke.

**Primer teksta:** *"This project will generate a primary dataset consisting of raw and derived measurements from the \[instrument X\], estimated at approximately \[X GB\], alongside a software/code output implementing the analysis pipeline used to produce the derived data. In addition, the project will reuse a third-party dataset from \[source/partner\], obtained under \[licence/agreement type\], to \[purpose, e.g. validate/complement the generated data\]."*

* Ako projekat ponovo koristi podatke trećih strana ili partnerske institucije (verovatno u zajedničkom projektu), to treba eksplicitno navesti ovde i naznačiti sve uslove vezane za ponovnu upotrebu — to se dalje odražava i na odgovor za *Accessible* niže u tekstu.  
* Ako veličina podataka zaista nije poznata u fazi prijave (čest slučaj), dati procenu reda veličine umesto preskakanja pitanja. "Veličina podataka je procenjena ispod 1 GB" je sasvim prihvatljiv odgovor.
* U ovom delu možete objasniti i koje ćete metode koristiti za organizaciju fajlova i foldera, iako se to u ovom delu ne traži. To pitanje imaćete svakako prilikom pisanja DMP-a, a ovde taj proces možete objasniti u par rečenica ukoliko to prostor za pisanje dozvoljava.

## **2\. Findability**

**Šta se pita:** [Perzistentni identifikatori](https://en.wikipedia.org/wiki/Persistent_identifier) (PID-ovi) i pouzdan repozitorijum koji će biti korišćen.

**Primer teksta:** *"The generated dataset (instrument data, both row and derived) and the accompanying analysis code will each be deposited as separate records in \[repository name\], each assigned a persistent identifier (\[DOI/Handle/ARK\]). The reused third-party dataset is identified by its own existing PID, \[DOI/Handle, if known\], issued by \[source repository\], which will be cited in the project's outputs and DMP. "*

Dodajte i jedan pasus u kojem ćete opisati izabrani repozitorijum(e). Možete iskoristiti ove delove za VinaR, Zenodo ili Github, a ukoliko koristite neki drugi repozitorijum, slobodno se obratite bibliotekarima za pomoć:

**VinaR**: “*VinaR is the institutional repository of the Vinča Institute of Nuclear Sciences, University of Belgrade, built on DSpace and developed in line with OpenAIRE interoperability guidelines. It assigns a persistent Handle identifier to every deposited record that doesn't already carry a DOI, describes metadata using the Qualified Dublin Core standard, and exposes records via both OAI-PMH and a REST API, enabling automatic harvesting by aggregators and search services such as OpenAIRE, BASE, and CORE. VinaR supports machine-readable licensing (Creative Commons for data; MIT, Apache, and GNU licenses for software) and can link deposited records to a researcher's ORCID.*”

**Zenodo**: “*Zenodo is a general-purpose open repository developed and operated by CERN and OpenAIRE, widely used across research disciplines when no domain-specific repository is available or suitable. It assigns a DOI to every deposit, supports versioning with a distinct DOI per version, and accepts a broad range of file formats and sizes. Zenodo integrates with GitHub for automatic archiving of software releases and supports the range of machine-readable licenses, including Creative Commons and standard open-source software licenses.”*

**GitHub**: *“GitHub is a code hosting and version control platform, commonly used during active development of analysis code, scripts, and software. It is not a long-term archival repository on its own — repositories can be deleted or accounts closed — so for research outputs intended for citation and long-term preservation, a GitHub release should be archived to a repository that assigns a persistent identifier, such as Zenodo (via its GitHub integration) or a dedicated software repository.”*

Specifičnosti VinaR-a, ukoliko se koristi: VinaR svakoj deponovanoj jedinici koja već ne nosi DOI dodeljuje **Handle PID**. Vredi ovo jasno navesti umesto da se pretpostavi da recenzenti to znaju — [Handle](https://en.wikipedia.org/wiki/Handle_System) je legitiman tip PID-a, ali manje poznat od DOI-ja, pa jedna dodatna napomena pomaže ("a persistent Handle identifier, resolvable in the same way as a DOI").

Ako se deponuje Zenodo treba da znate da imamo [Vinčinu Zenodo zajednicu](https://zenodo.org/communities/vins/records?q=&l=list&p=1&s=10&sort=newest) u koju možete prijaviti vaše skupove podataka ili softver koji deponujete u ovaj repozitorijum.

## **3\. Accessibility**

**Šta se pita:** razmatranja u vezi sa pravima intelektualne svojine, vremenski okvir za otvoreni pristup (obrazložiti ako otvoreni pristup nije ili neće biti omogućen), i mehanizmi pristupa ograničenim podacima radi verifikacije.

**Pristupačnost (Accessibility)** u okviru FAIR principa ne znači nužno da podaci moraju biti dostupni kao otvoreni podaci. Podrazumeva se da su podaci i njihovi metapodaci (opis skupa podataka, njegovo poreklo i uslovi pristupa) dostupni putem jasno definisanog, standardizovanog postupka što uključuje i situacije kada je pristup ograničen, odnosno uslovljen odobrenjem ili vremenskim embargom. Ono što je ključno jeste da metapodaci ostanu vidljivi čak i kada sami podaci nisu javno dostupni, i da postupak za dobijanje pristupa bude jasan i dokumentovan. Drugim rečima, podaci mogu biti zatvoreni ili ograničenog pristupa iz raznih opravdanih razloga, kao što su zaštita intelektualne svojine, ličnih podataka, ili ugovornih obaveza prema partneru, a da i dalje ispunjavaju zahtev principa Pristupačnosti, pod uslovom da je jasno definisano ko, kako i pod kojim uslovima može zatražiti pristup.

Ipak, treba znati da je prema članu 47 stav 3 Akta Zajedničkog istraživačkog programa naučnika iz RS i NRK “važe principi otvorene nauke, u skladu sa [*Platformom za otvorenu nauku 2.0*](https://nitra.gov.rs/images/nauka/TONuS-Platforma_2.0-Final.pdf) Ministarstva nauke, tehnološkog razvoja i inovacija Republike Srbije.“ Prema ovoj nacionalnoj politici otvoreni pristup podacima koji su poslužili kao osnova za publikacije je obavezan, osim ako postoji konkretan razlog za suprotno. Preporuka je da krenete od namere da se podaci dele otvoreno, a mehanizme ograničenja uvesti samo tamo gde postoji stvaran sukob interesa ili namera da se rezultati prijave za zaštitu intelektualne svojine.

**Primer teksta:** *"The generated dataset will be embargoed for \[X months\] to allow for patent filing based on the instrument X measurements, after which it will be made openly available under a CC BY 4.0 licence via \[repository\]. The accompanying analysis code will be released under an Apache 2.0 licence via \[repository/GitHub\], twelve months after project end. The reused third-party dataset remains subject to the access conditions set by its original provider; this project's use of it complies with \[licence/Data Use Agreement (DUA) terms\], and no redistribution of the original dataset is planned beyond what those terms permit."* 

**Napomena o intelektualnoj svojini i patentima.** Bilateralni projekti sa inostranim (u ovom slučaju kineskim)  institucijama mogu pokrenuti pitanja intelektualne svojine iz dva razloga: rokovi za prijavu patenata (podaci objavljeni pre patentne prijave mogu ugroziti novost izuma), i kineski propisi o izvozu i bezbednosti podataka, koji mogu biti stroži od onoga na šta su istraživači sa Vinče navikli u saradnji sa partnerima iz EU. Ako je bilo šta od ovih razloga slučaj onda:

* to treba jasno navesti, umesto da se podrazumeva puni otvoreni pristup u nadi da problem neće isplivati kasnije. Recenzentu je uverljivije "razmislili smo o ovome i evo plana" nego obećanje otvorenog pristupa koje se u fazi deponovanja pokaže neizvodljivim.  
* treba navesti konkretan mehanizam, ne samo izreći da je “pristup ograničen": tipične opcije su embargo vezan za prijavu patenta (*"data will be embargoed for up to 18 months to allow patent application; the metadata record will be public immediately"*), ugovor o korišćenju podataka (Data Use Agreement) za pristup radi verifikacije bez punog javnog objavljivanja, ili — ako zaista ništa ne može biti podeljeno — zatvoren skup podataka sa otvorenim metapodacima u repozitorijumu.  
* ako ograničenje proizlazi iz politika partnerske institucije ili nacionalnih propisa (a ne iz odluke na nivou projekta), to treba navesti kao razlog, umesto da ostane neobjašnjeno.  
* vidljivost samo na nivou metapodataka (naslov, apstrakt, PID, bez mogućnosti pristupa fajlu u repozitorijumu) legitimna je srednja opcija kada je potpuno zatvaranje neophodno.

**Pristup radi verifikacije:** čak i za zatvorene ili embargovane podatke, treba ukratko navesti na koji način bi recenzent ili revizor mogao proveriti da podaci zaista postoje i odgovaraju navodima.

## **4\. Interoperability**

**Šta se pita:** standardi, formati i rečnici za podatke i metapodatke.

**Primer teksta:** *"Raw instrument data from \[instrument X\] will be converted from its native/proprietary output format to \[open format, e.g. CSV, HDF5\] for deposit, with derived data described using \[metadata standard\]. The analysis code will include a README and dependency manifest (e.g. requirements.txt/environment.yml) to document the software environment needed to reproduce the derived data from the raw data. The reused third-party dataset is provided in \[format\]; where necessary, this project's derived outputs will note any transformation applied to it for interoperability with the generated data."*   

Repozitorijum koji koristite za čuvanje podataka opisuje podatke u skladu sa nekim od standardizovanih metapodataka. Tu informaciju možete najčešće naći u politikama na samom sajtu ili u delovima koji bliže opisuju rad i funkcionisanje samog repozitorijma.  

Specifičnosti VinaR-a: metapodaci su standardizovani prema **Qualified Dublin Core** šemi, a zapisi su dostupni i preko **OAI-PMH** protokola i preko **REST API-ja**, što omogućava spoljnim agregatorima (OpenAIRE, BASE, CORE) da automatski preuzmu zapis. Ako se deponuje u VinaR, jedna rečenica koja pominje Dublin Core i mehanizam agregacije u potpunosti pokriva ovu podtačku.

Ako je sirovi izlaz sa instrumenta u vlasničkom (proprietary) formatu (čest slučaj kod spektroskopije, snimanja (*imaging*), termalne analize), to treba navesti i poželjno je konvertovati ga u otvoren format za deponovanje radi lakšeg i efikasnije ponovnog korišćenja i deljenja.

## **5\. Ponovna upotrebljivost (Reusability)**

**Šta se pita:** licenca za podatke i ponovnu upotrebu, i dostupnost alata/softvera potrebnih za tumačenje ili ponovnu upotrebu podataka.

**Primer teksta:** *"The generated dataset will be released under a CC BY 4.0 licence upon expiry of the embargo, permitting reuse with attribution. The analysis code will be released under an Apache 2.0 licence, permitting reuse, modification, and redistribution under the same terms, from twelve months after project end. The reused third-party dataset carries its own licence/terms of use, \[state licence\], which govern any further reuse of it independent of this project's outputs; this project's own outputs derived from it will be released under \[licence\], consistent with what the source licence permits."* 

Specifičnosti VinaR-a: VinaR podržava mašinski čitljive licence — Creative Commons (CC licence) za podatke i standardne softverske licence za kod — tako da se odabrana licenca vezuje za zapis u obliku koji drugi sistemi mogu automatski da očitaju, a ne samo kao rečenica u opisu.

* Ako razmatranja u vezi sa intelektualnom svojinom ili patentima ograničavaju izbor licence (u vezi sa tačkom *Accessibility*), licenca strožija od CC BY (*Creative Commons Attribution*) je ovde legitiman izbor — to treba navesti dosledno sa odgovorom za *Accessibility*, umesto da se tamo obeća CC BY, a ovde nešto strože.  
* Ako su prilagođen kod, modeli ili analitički tokovi rada suštinski za tumačenje podataka, to treba eksplicitno navesti. Neobjavljivanje koda koji je potreban zbog ponovne upotrebljivosti skupova podataka čini reproducibilnost nalazi praktično nemogućim.

## **6\. Upravljanje, čuvanje i odgovornost**

**Šta se pita:** ko je odgovoran za upravljanje podacima i kontrolu kvaliteta, i koliki su troškovi.

**Primer teksta:** *"Data management and quality assurance across the three outputs — the generated instrument dataset, the analysis code, and the reused third-party dataset — will be coordinated by \[named role, e.g. project PI\], with deposit and embargo management support from the \[institution name\] repository service. Storage during the active project phase, including the embargoed dataset and code, is covered under \[budget line/institutional infrastructure\], at negligible additional cost given free deposit in \[repository, i.e. VinaR/Zenodo\] and \[code repository\]."* 

* Navesti konkretnu osobu ili ulogu, a ne "tim" — recenzenti navedenu odgovornu osobu čitaju kao znak da je plan ozbiljno promišljen, a ne opšte mesto.  
* Ako se očekuje da biblioteka pruža podršku pri deponovanju, sasvim je u redu, čak i korisno, eksplicitno navesti tu vezu podrške: "with support from the Institute's repository and Open Science service" ukazuje na postojanje institucionalne infrastrukture, što recenzenti gledaju povoljno.  
* Troškovi ne postoje za institucionalno deponovanje (VinaR) ili za Zenodo (besplatno deponovanje podataka), međutim neki repozitorijumi, pogotovo disciplinarni, naplaćuju deponovanje (obično su to troškovi uređivanja metapodataka, transformacije formata i sl). Ovo su legitimni troškovi i treba ih navesti.

