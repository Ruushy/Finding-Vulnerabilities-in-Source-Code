# Finding Vulnerabilities in Source Code



بسم الله الرحمن الرحيم

qoraakaan ai ayaan isticmaalay si uu format fiican ugu sameeyo github hadii aad aragto khalad ama wax is daba marsan yihiin fadlan akhri halka aan soo dhignay qoraalka asalka ah waa kanaa [https://telegra.ph/Finding-Vulnerabilities-in-Source-Code-02-10](https://telegra.ph/Finding-Vulnerabilities-in-Source-Code-02-10)

---

## Table of Contents

1. [Hordhaca Falanqaynta Koodhka iyo Hababka Loo Wajaho](#1-hordhaca-falanqaynta-koodhka-iyo-hababka-loo-wajaho)

1. [Black-Box vs. White-Box Testing](#2-black-box-vs-white-box-testing)

1. [Habka Loo Maro Falanqaynta Koodhka](#3-habka-loo-maro-falanqaynta-koodhka)

1. [Static vs. Dynamic Analysis (SAST vs. DAST)](#static-vs-dynamic-analysis-sast-vs-dast)

1. [Qalabka Falanqaynta Koodhka](#qalabka-falanqaynta-koodhka)

1. [Aqoonsiga Saxiixyada Nuglaanshaha - XSS iyo SQL Injection](#aqoonsiga-saxiixyada-nuglaanshaha---xss-iyo-sql-injection)

1. [Aqoonsiga Saxiixyada Nuglaanshaha - Path Traversal, Command Injection, iyo Backdoors](#aqoonsiga-saxiixyada-nuglaanshaha---path-traversal-command-injection-iyo-backdoors)

1. [Falanqaynta Koodhka Java](#falanqaynta-koodhka-java---meelaha-laga-helo-xogta-iyo-api-yada-halista-ah)

1. [Falanqaynta Koodhka Perl iyo JavaScript](#falanqaynta-koodhka-perl-iyo-javascript-client-side)

1. [Falanqaynta Koodhka Database-ka](#falanqaynta-koodhka-database-ka-database-code-components)

---

## 1. Hordhaca Falanqaynta Koodhka iyo Hababka Loo Wajaho

### Waa Maxay Falanqaynta Koodhka (Code Review)?

Halkii aad ka weerari lahayd website-ka adigoo isticmaalaya browser-kaaga (**black-box**), waxaad si toos ah u eegaysaa koodhka uu ka samaysan yahay (**white-box**). Tani waxay la mid tahay inaad hesho naqshaddii dhismaha oo dhan halkii aad ka isku dayi lahayd inaad albaabada jebiso.

### Goorma Ayaad Heli Kartaa Koodhka?

- **Open Source**: Haddii website-ku uu isticmaalo software furan (sida WordPress, Joomla, Magento).

- **Penetration Testing**: Marka shirkad ay ku shaqaaleysiiso si aad amnigeeda u hubiso, waxay ku siin karaan koodhka.

- **File Disclosure**: Haddii aad hesho nuglaansho kale (sida Path Traversal) oo kuu oggolaanaya inaad soo dejisato faylasha koodhka.

- **Client-Side Code**: Koodhka JavaScript-ka mar walba waa la heli karaa.

---

## 2. Black-Box vs. White-Box Testing

### Black-Box (Weerarka Dibadda)

| Awoodiisa | Daciifnimadiisa |
| --- | --- |
| Degdeg, wuxuu si fiican u helaa nuglaanshooyinka caadiga ah, wuxuu tijaabiyaa sida dhabta ah ee uu website-ku u shaqeeyo. | Ma arki karo ciladaha logic ah ee qarsoon, wuxuu seegi karaa nuglaanshooyin badan. |

### White-Box (Falanqaynta Koodhka)

| Awoodiisa | Daciifnimadiisa |
| --- | --- |
| Wuxuu helaa nuglaanshooyin oo aan la arki karin (sida "backdoors", cilado logical ah), wuxuu bixiyaa 100% daboolid (coverage). | Waqti badan ayuu qaataa, wuxuu u baahan yahay faham aasaasi ah oo luqadda ah. |

### Grey-Box (Habka Isku Dhafan)

Habka ugu fiican waa in la isku daro labadaba. Markaad hesho calaamad yar oo "black-box" ah, waxaad u laabanaysaa koodhka si aad u xaqiijiso.

---

## 3. Habka Loo Maro Falanqaynta Koodhka

Hab saddex-geesood ah oo aad wax ku ool u ah:

1. **Raad-raac Xogta Isticmaalaha**: Ka bilow meesha xogta laga soo geliyo (sida `$_GET['id']`), oo raac halka ay marto, sida loo isticmaalo, iyo meesha ay ku dambayso. Tani waa habka ugu fiican ee lagu helo "injection flaws".

1. **Raadi Nuglaanshaha Signatures**: Raadi erayo ama calaamado caan ah oo muujinaya nuglaansho. Tusaale, raadi `SELECT * FROM` si aad u hesho SQLi, ama `eval(` si aad u hesho Code Injection.

1. **Falanqee Koodhka Halista ah (Review Risky Code)**: Si gaar ah u eeg qaybaha ugu muhiimsan sida bogagga "login"-ka, "password reset", iyo meelaha faylasha laga soo geliyo.

---

## Static vs. Dynamic Analysis (SAST vs. DAST)

- **SAST (Static Application Security Testing)**: Waa falanqaynta koodhka isagoo aan shaqaynayn. Waa waxa aan hadda baranayno.

- **DAST (Dynamic Application Security Testing)**: Waa baaritaanka website-ka isagoo shaqaynaya (sida Burp Scanner).

- **IAST (Interactive Application Security Testing)**: Waa teknoolajiyad cusub oo isku darta labadaba, iyadoo "agent" la geliyo server-ka si uu ula socdo sida xogtu ugu dhex marto.

---

## Qalabka Falanqaynta Koodhka

Falanqaynta koodhka uma baahnid qalab adag. Waxaad u baahan tahay oo kaliya:

### Tafatiraha Koodhka

Sida **Visual Studio Code (VS Code)**. Wuxuu leeyahay awoodo ay ka mid yihiin:

- **Global Search**: Waxaad ka raadin kartaa eray gaar ah dhammaan faylasha mashruuca.

- **Kala Soocid Luqadeed**: Wuxuu kuu midabaynayaa koodhka si aad si fudud u kala garato.

- **Go to Definition**: Waxaad si fudud ugu boodi kartaa meesha "function" ama "variable" lagu qeexay.

### Grep

Waa qalab "command-line" ah oo awood badan oo loo isticmaalo in laga dhex raadiyo qoraal faylasha. Waa mid aad u dheereeya marka la baarayo koodh aad u weyn.

> **Tusaale:** `grep -r "SELECT" /path/to/source_code/`

---

## Aqoonsiga Saxiixyada Nuglaanshaha - XSS iyo SQL Injection

### 1. Saxiixa Cross-Site Scripting (XSS)

Raadi meel kasta oo xog ka timid isticmaalaha lagu dhex daabacayo bogga HTML-ka ah (**sink**) iyadoon la marin sifeyn habboon (sida `htmlspecialchars` ee PHP).

#### Saxiixa Ugu Cad

Koodh isku daraya HTML iyo "variable" ka yimid isticmaalaha.

**Tusaale (ASP.NET):**

```
String link = "<a href=" + ... + Request.QueryString["refURL"] + ... + "</a>";
objCell.InnerHtml = link;
```

Halkan, `Request.QueryString` waa **source**, `InnerHtml` waa **sink**. Maadaama la dhisayo HTML, ma sahlana in la isticmaalo "encoding" ka dib, taasoo ka dhigaysa meel aad halis u ah.

**Tusaale kale (PHP):**

```php
echo "Welcome, " . $_GET['name'];
```

Kani waa saxiixa ugu fudud ee XSS. `$_GET['name']` waa **source**, `echo` waa **sink**.

#### Saxiixa Qarsoon

Mararka qaarkood, xogta isticmaalaha waxaa la geliyaa "variable" ka dibna meel kale ayaa lagu isticmaalaa.

**Tusaale (Java):**

```java
if ("3".equals(requestType)) {
    m_pageTitle = request.getParameter("title"); 
}
// ... meel kale oo koodhka ka mid ah ...
out.println("<title>" + m_pageTitle + "</title>");
```

Halkan, waa inaad raacdaa isticmaalka `m_pageTitle` si aad u hesho nuglaanshaha. Tani waxay muujinaysaa muhiimadda ay leedahay in la raadraaco socodka xogta.

### 2. Saxiixa SQL Injection (SQLi)

Raadi meel kasta oo xog ka timid isticmaalaha (**source**) si toos ah loogu dhex darayo (concatenated) weydiin SQL ah (**sink**) iyadoon la isticmaalin "Parameterized Queries".

#### Saxiixa Ugu Cad

Koodh dhisaya weydiin SQL ah iyadoo la isku dhejinayo qoraallo iyo "variables".

**Tusaale (ASP.NET):**

```
SqlQuery.Append(" AND CustomerID = ");
SqlQuery.Append(Request.QueryString["CID"].ToString());
```

Halkan, `Request.QueryString` waa **source**, `SqlQuery` oo markii dambe la ekzekiyuutin doono waa **sink**.

**Tusaale kale (PHP):**

```php
$query = "SELECT * FROM users WHERE username = '" . $_POST['username'] . "'";
mysql_query($query);
```

Kani waa saxiixa ugu caansan ee SQLi ee PHP.

Habka ugu fiican waa in la raadiyo qaybo ka mid ah weydiimaha SQL, sida: `"SELECT "`, `" WHERE "`, `" AND "`. Raadintani waxay si degdeg ah kuu tusinaysaa meelaha ay u badan tahay in lagu dhiso weydiimo SQL ah.

#### Second-Order SQL Injection

Tani waxay dhacdaa marka xogta marka hore si ammaan ah loo geliyo database-ka (iyadoo la isticmaalayo "escaping"), laakiin marka dib looga soo akhriyo database-ka, si aan ammaan ahayn loogu isticmaalo weydiin kale. Markaad falanqaynayso koodhka, ha eegin oo kaliya meelaha `$_GET` iyo `$_POST` laga isticmaalo, laakiin sidoo kale eeg meelaha xog laga soo akhriyay database-ka dib loogu isticmaalayo weydiin kale.

---

## Aqoonsiga Saxiixyada Nuglaanshaha - Path Traversal, Command Injection, iyo Backdoors

### 1. Saxiixa Path Traversal

Raadi meel kasta oo xog ka timid isticmaalaha (**source**) loo isticmaalayo in lagu dhiso waddo fayl (file path), ka dibna lagu furo ama lagu akhriyo faylkaas (**sink**) iyadoon la hubin in xogtu ay ka baxsanayso galka loogu talagalay.

#### Saxiixa Ugu Cad

Koodh isku daraya waddo go'an iyo "variable" ka yimid isticmaalaha, ka dibna u gudbinaya "function" faylasha maareeya.

**Tusaale (ASP.NET):**

```
FileStream fsAttachment = new FileStream(SpreadsheetPath + HttpUtility.UrlDecode(Request.QueryString["AttachName"]), FileMode.Open, ...);
```

Halkan, `Request.QueryString["AttachName"]` waa **source**, `FileStream` waa **sink**. Isku-darka tooska ah waa calaamad halis ah.

**Tusaale kale (PHP):**

```php
$file_to_include = $_GET['page'];
include($file_to_include); 
```

Kani waa saxiixa caadiga ah ee Local File Inclusion (LFI).

**Sida Loo Raadiyo**: Raadi magacyada "functions"-ka la xiriira faylasha (sida `FileStream`, `fopen`, `include`, `require`) oo eeg haddii ay si toos ah u isticmaalayaan xog ka timid isticmaalaha.

### 2. Saxiixa OS Command Injection

Raadi meel kasta oo xog ka timid isticmaalaha (**source**) lagu dhex darayo amar loo dirayo "operating system"-ka (**sink**).

#### Saxiixa Ugu Cad

Isticmaalka "functions" si toos ah u fuliya amarrada OS-ka.

**Tusaale (Perl):**

```
$command = "du -h --exclude php* /var/www/html";
$command = $command . param("dir");
$command = `$command`; // Backticks-ku waxay fuliyaan amarka
```

Halkan, `param("dir")` waa **source**, backticks waa **sink**.

**Tusaale kale (PHP):**

```php
$target = $_REQUEST['ip'];
$cmd = shell_exec('ping -c 4 ' . $target);
```

`$_REQUEST['ip']` waa **source**, `shell_exec` waa **sink**.

Raadi magacyada "functions"-ka halista ah sida `system`, `exec`, `shell_exec`, `passthru`, `popen`, iyo backticks (``).

### 3. Saxiixa Backdoors iyo Ciladaha Macquulka ah

Kuwani ma laha saxiix joogto ah, laakiin waxay inta badan ka dhashaan koodh u muuqda mid aan caadi ahayn ama leh "shortcuts".

**Tusaale (Backdoor Password):**

```java
if (checkCredentials(up, password) || "oculiomnium".equals(password))
    return up;
```

Halkan, `|| "oculiomnium".equals(password)` waa backdoor. Waa furaha sirta ah ee master-ka ah ee shaqeeya iyadoon loo eegin username-ka.

#### Variable Functions (PHP)

Sidaan horay u soo sheegnay, PHP wuxuu oggol yahay in magaca "function"-ka laftiisa laga dhigo "variable".

```php
$my_function = $_GET['function_name'];
$my_function(); // Tani waxay fulinaysaa function-ka uu isticmaaluhu soo qoray
```

Raadinta `$_GET['...']()` waa saxiix aad u halis badan.

### Sida Loo Raadiyo

- **Raadi qoraallo adag**: Raadi furayaal sir ah, furayaal API, ama URL-yo qarsoon oo si toos ah loogu dhex qoray koodhka.

- **Raadi Faallooyin**: Raadi erayo sida `TODO`, `FIXME`, `HACK`, `BUG`. Developers inta badan waxay uga tagaan calaamado naftooda, kuwaas oo adiga kuu noqon kara khariidad.

- **Eeg Ciladaha logical ah**: Raadi meelaha `if` loo isticmaalay si aan caadi ahayn, gaar ahaan meelaha la xiriira hubinta aqoonsiga ama xuquuqda.

---

## Falanqaynta Koodhka Java - Meelaha Laga Helo Xogta iyo API-yada Halista ah

### 1: Sida Loo Helo Xogta Isticmaalaha

Si ka duwan PHP oo isticmaala "superglobals" sida `$_GET`, Java wuxuu isticmaalaa "objects" iyo "methods" si uu u helo xogta codsiga. Meesha ugu muhiimsan ee laga bilaabo waa `HttpServletRequest` object.

#### API-yada Muhiimka ah (Sinks)

- `request.getParameter("name")`: Kani waa habka ugu caansan ee lagu helo hal "parameter". Waa isku-darka `$_GET` iyo `$_POST`.

- `request.getParameterValues("name")`: Wuxuu soo celiyaa "array" haddii "parameter"-ka la soo diro marar badan (HPP).

- `request.getHeader("User-Agent")`: Wuxuu helayaa "HTTP headers".

- `request.getCookies()`: Wuxuu helayaa "cookies".

- `request.getQueryString()`: Wuxuu soo celiyaa dhammaan "query string"-ka oo aan la kala saarin.

- `request.getInputStream()`: Wuxuu si toos ah u akhriyaa request body.

Markaad falanqaynayso koodhka Java, raadi meel kasta oo `request.getParameter` ama `request.getHeader` la isticmaalay. Kuwani waa meelaha ay xogta isticmaaluhu ka soo gasho.

### 2. API-yada Halista ah (Potentially Dangerous APIs)

PHP wuxuu leeyahay "wrappers" awood badan oo lagu maareeyo xogta. Tusaale, `php://input` wuxuu si toos ah u akhriyaa jirka body POST. Haddii tan loo isticmaalo `include()`, waxay horseedi kartaa RCE: `include('php://input');`

#### Object Injection (Deserialization)

Haddii website-ku uu isticmaalo `unserialize()` oo uu ku jiro xog ka timid isticmaalaha, waxay horseedi kartaa RCE iyadoo la adeegsanayo "magic methods" sida `__wakeup()` ama `__destruct()`.

---

## Falanqaynta Koodhka Perl iyo JavaScript (Client-Side)

### 1. Falanqaynta Koodhka Perl

Perl waa luqad duug ah laakiin weli laga helo meelaha qaarkood, gaar ahaan "scripts"-ka CGI. Waxay leedahay habab u gaar ah oo ay xogta ku hesho iyo "functions" halis ah.

#### Sida Loo Helo Xogta Isticmaalaha (Sources):

- **CGI.pm module**: Kani waa "module"-ka ugu caansan. Wuxuu isticmaalaa `param('name')` si uu u helo xogta.

- **%in hash**: Hab duug ah oo si toos ah u abuuraya "hash" ay ku jiraan dhammaan "parameters"-ka.

#### API-yada Halista ah (Sinks)

- `open()`: Kani waa kan ugu halista badan Perl. Haddii loo isticmaalo qaabka `open(FH, "| command")`, wuxuu si toos ah u fulinayaa amar OS ah.

- `system()`, `exec()`, backticks (``): Sida luqadaha kale, kuwani waxay fuliyaan amarrada OS-ka.

- `eval()`: Wuxuu fuliyaa koodh Perl ah oo "string" ah.

**Taint Mode (-T)**: Perl wuxuu leeyahay hab difaac ah oo la yiraahdo "Taint Mode". Wuxuu si otomaatig ah u calaamadiyaa dhammaan xogta ka timaada isticmaalaha ("tainted"). Uma oggolaanayo in xogtaas "tainted" ah loo isticmaalo "functions"-ka halista ah ilaa si cad loo nadiifiyo iyadoo la isticmaalayo "regular expression". Tani waa difaac fiican, laakiin haddii "regex"-ka la isticmaalay uu qaldan yahay, weli waa la jabin karaa.

### 2. Falanqaynta Koodhka JavaScript (Client-Side)

Halkan, ma raadineyno SQLi ama Command Injection. Waxaan raadineynaa **DOM-Based XSS**. Tani waxay dhacdaa marka JavaScript-ku uu xog ka akhriyo DOM-ka (sida URL-ka) oo uu si aan ammaan ahayn ugu qoro bogga.

#### Sources (Meelaha Xogta laga Akhriyo):

- `document.location`

- `document.URL`

- `document.referrer`

- `window.location`

- `location.hash` (Qaybta URL-ka ee ka dambaysa #)

#### Sinks (Meelaha Xogta lagu Qoro):

- `document.write()`

- `document.writeln()`

- `element.innerHTML`

- `eval()`

- `setTimeout()` / `setInterval()` (haddii "string" loo gudbiyo)

#### Saxiixa DOM-Based XSS

Raadi meel kasta oo mid ka mid ah "sources"-ka kor ku xusan loo gudbiyo mid ka mid ah "sinks"-ka iyadoon la sifeyn.

**Tusaale:**

```javascript
var url = document.location;
var message = url.substring(url.indexOf('message=') + 8);
document.write(message); // HALIS!
```

Halkan, `document.location` waa **source**, `document.write` waa **sink**.

#### DOM Clobbering

Waa farsamo weerar oo casri ah oo lagu beddelo "objects" JavaScript ah iyadoo la abuurayo "elements" HTML ah oo leh `id` ama `name` la mid ah magaca "object"-ka. Tani waxay jahawareerin kartaa koodhka JavaScript-ka waxayna horseedi kartaa XSS.

---

## Falanqaynta Koodhka Database-ka (Database Code Components)

### 1. Waa Maxay Database Code Components?

Developers-ka inta badan waxay qoraan koodh si toos ah ugu dhex shaqeeya database-ka si ay u dedejiyaan shaqooyinka ama u hirgeliyaan "business logic" adag. Koodhkan wuxuu leeyahay awood la mid ah tan database-ka, taasoo ka dhigaysa mid aad halis u ah haddii cilad laga helo.

#### Noocyada Ugu Caansan:

- **Stored Procedures**: Waa "functions" SQL ah oo la sii qoray oo la kaydiyay, kuwaas oo lagu fulin karo hal amar.

- **Triggers**: Waa koodh si otomaatig ah u shaqeeya marka waxqabad gaar ah (sida INSERT, UPDATE) uu ka dhaco "table" gaar ah.

- **User-Defined Functions (UDFs)**: Waa "functions" uu developer-ka isagu qoray si uu u kordhiyo awoodaha database-ka.

### 2. Nuglaanshooyinka Ugu Caansan

#### SQL Injection (Second-Order)

Kani waa kan ugu halista badan. Xitaa haddii website-ku uu si ammaan ah u isticmaalo "Parameterized Queries" si uu ula hadlo "stored procedure", haddii "stored procedure"-ka laftiisu uu si aan ammaan ahayn u dhiso weydiin kale oo "dynamic" ah, waxaa dhacaya SQL Injection.

**Tusaale (MS-SQL):**

```sql
CREATE PROCEDURE show_current_orders (@name varchar(400))
AS
DECLARE @sql nvarchar(4000)
-- HALIS: Xogta isticmaalaha si toos ah ayaa loogu darayaa weydiinta
SELECT @sql = 'SELECT ... WHERE searchstring = ''' + @name + ''''
EXEC (@sql) -- Fulinta weydiinta dynamic-ka ah
GO
```

Halkan, xitaa haddii `@name` si ammaan ah loo soo gaarsiiyo, `EXEC (@sql)` ayaa sababaya nuglaanshaha.

**Sida Loo Raadiyo**: Raadi "keywords"-ka fulinta "dynamic"-ka ah ee database kasta: `EXEC` (MS-SQL), `EXECUTE IMMEDIATE` (Oracle).

#### Privilege Escalation

Gaar ahaan Oracle, "stored procedures" waxay inta badan ku shaqeeyaan xuquuqda qofkii abuuray (**Definer's Rights**), ee maaha qofka fulinaya (**Invoker's Rights**).

**Khatarta**: Haddii maamulaha database-ka (DBA) uu abuuro "procedure" nugul, weeraryahan leh akoon awood yar wuxuu ka faa'iidaysan karaa nuglaanshahaas si uu u helo awoodda DBA.

#### U yeeridda "Functions" Halis ah

"Stored procedures" waxay u yeeri karaan "functions" kale oo halis ah oo ku jira database-ka ama OS-ka.

**Tusaale (MS-SQL):**

```sql
CREATE PROCEDURE import_data (@loadfile varchar(25), ...)
AS
...
exec @ret = xp_cmdshell '...' + @loadfile -- HALIS!
...
End
```

Haddii weeraryahanku uu maareyn karo `@loadfile`, wuxuu fulin karaa amar OS ah.

**Sida Loo Raadiyo**: Raadi magacyada "functions"-ka halista ah sida `xp_cmdshell` (MS-SQL), `UTL_HTTP` (Oracle), `LOAD_FILE` (MySQL).

#### Triggers-ka Qarsoon

"Triggers"-ku waa kuwo aad u khiyaano badan sababtoo ah si toos ah looma fuliyo. Waxay shaqeeyaan oo kaliya marka xog la geliyo "table" gaar ah. Markaad falanqaynayso koodhka, waa inaad sidoo kale eegtaa "triggers"-ka ku xiran "tables"-ka ay xogtaadu saameyneyso.

