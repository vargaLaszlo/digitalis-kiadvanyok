# Az internetről dióhéjban

A felhasználók akik igénybe akarnak venni egy szolgáltatást az interneten, internetképes eszközeikkel tehetik meg ezt \(ez lehet hagyományos számítógép, okostelefon, konzol, még akár egy hűtőszekrény is\). Az eszközön lévő böngésző vagy egyéb alkalmazás \(kliens\) egy kérést küld az interneten keresztül a kiszolgálónak \(szerver\). A kiszolgáló a kérésnek \(request\) megfelelően összeállítja a választ \(response\) csomagok formájában, és visszaküldi a kliensnek. A válaszként kapott csomagok alapján jeleníti meg a felhasználó gépén a kliens például a lekért weboldalt.

![](.gitbook/assets/net.png)

A szerver vagy kiszolgáló területét nevezzük backend-nek, a kliens oldal területét frontend-nek, vagy kliens oldalnak.

![](.gitbook/assets/3for1.png)

Kliens oldalán alkotóelemeire bontva egy weboldalt, három fő elkülöníthető technológiát tudunk azonosítani:

Az első a **HTML**, vagy hipertext jelölőnyelv, ez a szabvány a weboldalak strukturális felépítését \(tartalmi szerkezetét\) biztosítja.  
A második a **CSS**, vagy egymásba ágyazható stíluslapok, ami a weboldalak megjelenéséért felel.  
A harmadik a **JavaScript**, ami a web programozási nyelve, és a weboldalak viselkedését vezérli.

A kiszolgáló oldalán némileg összetettebb a helyzet, számtalan megoldással találkozhatunk. Napjainkban  a hagyományos weboldalak között igen elterjedt de közel sem az egyetlen megoldás, hogy a kiszolgálón egy PHP szerver oldali scriptnyelv futtatására alkalmas Unix környezet fut \(LAMP - Linux Apache MySql PHP\), maga a weboldal "programja" egy tartalomkezelő rendszer, ilyen például a Wordpress, vagy a Drupal.

{% hint style="info" %}
Hogyan találja meg a beírt webcímhez tartozó szervert a böngészőnk? A webszerverek nem rendelkeznek nevesített címmel, amin elérhetjük őket az az IP címük \(Internet Protokoll cím\), ezt használják a számítógépek egymás azonosítására. Az IP címek hasonlítanak a telefonszámokra, a felhasználók számára nehezen olvasható, és megjegyezhető számsorozatokból állnak, példaként egy népszerű magyar internetes oldal IP címe: [79.172.213.245](http://194.143.245.39/). De hogy lesz ebből .hu végződésű domain név?  A böngészők lekérik az adott webcímhez, vagy domain-hez tartozó IP címet a DNS \(Domain Name System\) kiszolgálóktól. A DNS kiszolgálók vagy szerverek hálózata egyfajta internetes telefonkönyvként működik. A böngésző először lekéri a webcímhez tartozó IP címet \(feloldja\) a DNS hálózat szervereitől, ezután küldi el a kérést az IP címen található webszervernek \(request\). Természetesen a mi számítógépünk is rendelkezik az interneten IP címmel, erre küldi el a választ \(response\) a webszerver.
{% endhint %}

