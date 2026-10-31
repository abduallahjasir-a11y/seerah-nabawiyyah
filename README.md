<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>رحلة السيرة النبوية | من المولد إلى الوفاة</title>
<meta name="description" content="موقع تفاعلي يروي السيرة النبوية بالتسلسل التاريخي من مولد النبي ﷺ عام الفيل إلى وفاته، مع خط زمني متحرك وتفاصيل كل حدث.">
<meta property="og:title" content="رحلة السيرة النبوية">
<meta property="og:description" content="خط زمني تفاعلي للسيرة النبوية من الألف إلى الياء.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Amiri:wght@400;700&family=Tajawal:wght@400;500;700&display=swap" rel="stylesheet">
<style>
:root{--ink:#10151d;--ink2:#1b2330;--gold:#f2b83b;--gold2:#c98f12;--cream:#fdf3d6;--mut:#aab2c0;--r:14px}
*{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth;scroll-padding-top:70px}
body{background:var(--ink);color:var(--cream);font-family:Tajawal,sans-serif;line-height:1.9;overflow-x:hidden}
canvas#sky{position:fixed;inset:0;z-index:0;pointer-events:none}
#bar{position:fixed;top:0;right:0;height:4px;width:0;background:var(--gold);z-index:50}
nav{position:fixed;top:4px;left:0;right:0;z-index:40;display:flex;gap:8px;justify-content:center;padding:10px;background:linear-gradient(var(--ink),transparent);flex-wrap:wrap}
nav button{font:500 .9rem Tajawal;color:var(--cream);background:rgba(27,35,48,.85);border:1px solid #3a4558;padding:4px 16px;border-radius:99px;cursor:pointer;transition:.25s}
nav button:hover,nav button.on{background:var(--gold);color:var(--ink);border-color:var(--gold)}
button:focus-visible{outline:3px solid var(--gold);outline-offset:2px}
header{position:relative;z-index:1;min-height:100vh;display:grid;place-content:center;text-align:center;padding:90px 20px 40px}
header h1{font:700 clamp(3.2rem,12vw,8rem)/1.15 Amiri,serif;color:var(--gold);animation:rise 1.6s cubic-bezier(.2,.8,.2,1) both}
header p{max-width:560px;margin:14px auto 0;color:var(--mut);font-size:1.15rem;animation:rise 1.6s .5s cubic-bezier(.2,.8,.2,1) both}
.road{width:min(520px,80vw);margin:26px auto 0;display:block}
.road path{fill:none;stroke:var(--gold);stroke-width:5;stroke-linecap:round;stroke-dasharray:700;stroke-dashoffset:700;animation:draw 3.2s .3s ease forwards}
.go{margin-top:26px;color:var(--gold);font-size:.95rem;animation:bob 2s infinite}
@keyframes rise{from{opacity:0;transform:translateY(40px);filter:blur(8px)}to{opacity:1;transform:none;filter:none}}
@keyframes draw{to{stroke-dashoffset:0}}
@keyframes bob{50%{transform:translateY(8px)}}
main{position:relative;z-index:1;max-width:1000px;margin:0 auto;padding:0 18px 120px}
#spine{position:absolute;top:0;bottom:0;right:50%;width:3px;background:#2a3446;transform:translateX(50%)}
#fill{position:absolute;top:0;right:50%;width:3px;height:0;background:linear-gradient(var(--gold),var(--gold2));transform:translateX(50%);box-shadow:0 0 14px var(--gold)}
.era{position:relative;text-align:center;margin:90px 0 50px;padding:28px 10px;background:var(--ink);border-block:1px solid var(--gold2)}
.era h2{font:700 clamp(2rem,6vw,3.2rem) Amiri,serif;color:var(--gold)}
.era span{color:var(--mut)}
.ev{position:relative;width:50%;padding-bottom:46px;opacity:0;transition:opacity .8s,transform .8s cubic-bezier(.2,.8,.2,1)}
.ev.L{margin-right:50%;padding-right:38px;transform:translateX(-60px)}
.ev.R{margin-right:0;padding-left:38px;transform:translateX(60px)}
.ev.in{opacity:1;transform:none}
.ev::after{content:"";position:absolute;top:22px;width:18px;height:18px;border-radius:50%;background:var(--ink);border:4px solid var(--gold);transition:.4s}
.ev.L::after{right:-9px}
.ev.R::after{left:-9px}
.ev.in::after{box-shadow:0 0 0 7px rgba(242,184,59,.18)}
.card{display:block;width:100%;text-align:right;font:inherit;color:inherit;background:var(--ink2);border:1px solid #2f3a4c;border-radius:var(--r);padding:14px 16px 18px;cursor:pointer;transition:transform .3s,border-color .3s}
.card:hover{transform:translateY(-4px);border-color:var(--gold)}
.pic{height:110px;display:grid;place-items:center;font-size:3.4rem;border-radius:10px;margin-bottom:12px;overflow:hidden;background:radial-gradient(circle at 70% 20%,rgba(242,184,59,.35),transparent 60%),linear-gradient(135deg,#243049,#141b27)}
.pic img{width:100%;height:100%;object-fit:cover}
.card:hover .pic{font-size:3.8rem}
.pic{transition:font-size .3s}
.yr{color:var(--gold);font-weight:700;font-size:.95rem}
.card h3{font:700 1.6rem/1.5 Amiri,serif;margin:2px 0 4px}
.card p{color:var(--mut);font-size:1rem}
.more{display:inline-block;margin-top:6px;color:var(--gold);font-size:.9rem}
#modal{position:fixed;inset:0;z-index:100;display:grid;place-items:center;padding:16px;background:rgba(8,11,16,.8);backdrop-filter:blur(6px);opacity:0;pointer-events:none;transition:opacity .35s}
#modal.open{opacity:1;pointer-events:auto}
.box{position:relative;max-width:640px;width:100%;max-height:88vh;overflow:auto;background:var(--ink2);border:1px solid var(--gold2);border-radius:20px;padding:30px;transform:scale(.88) translateY(30px);transition:transform .45s cubic-bezier(.2,.9,.3,1.2)}
#modal.open .box{transform:none}
.box .pic{height:170px;font-size:5rem;margin-bottom:16px}
.box h3{font:700 2.2rem/1.4 Amiri,serif;color:var(--gold)}
.box p{margin-top:12px;font-size:1.08rem}
.box .lesson{margin-top:18px;padding:12px 16px;border-right:4px solid var(--gold);background:rgba(242,184,59,.08);border-radius:8px}
#x{position:absolute;top:12px;left:14px;width:40px;height:40px;border-radius:50%;border:1px solid #3a4558;background:rgba(16,21,29,.8);color:var(--cream);font-size:1.4rem;cursor:pointer;z-index:2}
#x:hover{background:var(--gold);color:var(--ink)}
.nav2{display:flex;justify-content:space-between;margin-top:22px;gap:10px}
.nav2 button{font:500 .95rem Tajawal;background:none;color:var(--gold);border:1px solid var(--gold2);border-radius:99px;padding:5px 18px;cursor:pointer}
.nav2 button:hover{background:var(--gold);color:var(--ink)}
footer{position:relative;z-index:1;text-align:center;padding:40px 20px 60px;color:var(--mut);border-top:1px solid #2a3446}
footer b{display:block;font:700 1.8rem Amiri,serif;color:var(--gold)}
@media(max-width:700px){
#spine,#fill{right:14px;transform:none}
.ev.L,.ev.R{width:100%;margin:0;padding:0 40px 36px 0;transform:translateY(40px)}
.ev.in{transform:none}
.ev.L::after,.ev.R::after{left:auto;right:6px}
.box{padding:24px 18px}
}
@media(prefers-reduced-motion:reduce){*{animation:none!important;transition:none!important}.ev,.ev.L,.ev.R{opacity:1;transform:none}.road path{stroke-dashoffset:0}}
</style>
</head>
<body>
<canvas id="sky" aria-hidden="true"></canvas>
<div id="bar"></div>
<nav aria-label="تنقل بين المراحل">
<button data-go="era0">قبل البعثة</button>
<button data-go="era1">العهد المكي</button>
<button data-go="era2">العهد المدني</button>
</nav>

<header>
<h1>السيرة النبوية</h1>
<p>رحلة عبر ثلاث وستين سنة، من مولد النبي ﷺ في مكة إلى وفاته في المدينة. اختر محطة واقرأ تفاصيلها.</p>
<svg class="road" viewBox="0 0 520 90" aria-hidden="true"><path d="M510 70 C 400 70, 380 15, 280 30 S 120 80, 10 20"/></svg>
<div class="go">انزل لتبدأ الرحلة ↓</div>
</header>

<main id="tl">
<div id="spine"></div><div id="fill"></div>
</main>

<div id="modal" role="dialog" aria-modal="true" aria-labelledby="mt">
<div class="box">
<button id="x" aria-label="إغلاق">×</button>
<div class="pic" id="mp"></div>
<div class="yr" id="my"></div>
<h3 id="mt"></h3>
<p id="md"></p>
<div class="lesson" id="ml"></div>
<div class="nav2"><button id="nx">الحدث التالي</button><button id="pv">الحدث السابق</button></div>
</div>
</div>

<footer><b>صلى الله عليه وسلم</b>مشروع مشارك في هاكثون السيرة النبوية، جامعة القصيم</footer>

<script>
/* لإضافة صورة حقيقية لأي حدث: ارفع الصورة في مجلد images داخل الريبو
   ثم أضف للحدث:  img:"images/اسم-الصورة.jpg"  */
const E=[
{era:0,t:"ما قبل البعثة",s:"٥٧٠م – ٦١٠م"},
{i:"🌙",y:"٥٧٠م · عام الفيل",t:"مولد النبي ﷺ",s:"وُلد يتيم الأب في مكة، في الثاني عشر من ربيع الأول على القول المشهور.",d:"وُلد محمد بن عبد الله بن عبد المطلب من بني هاشم في مكة، في العام الذي حاول فيه أبرهة هدم الكعبة فردّه الله. توفي أبوه عبد الله قبل ولادته، وأرضعته حليمة السعدية في بادية بني سعد.",l:"نشأ في بيئة ضعيفة الأسباب، وكان ذلك تمهيدًا لرسالة قائمة على التوكل على الله."},
{i:"🌿",y:"٥٧٦م · ٦ سنوات",t:"وفاة أمه ثم جده",s:"توفيت آمنة بنت وهب، ثم كفله جده عبد المطلب، ثم عمه أبو طالب.",d:"توفيت أمه آمنة في الأبواء وهي عائدة من المدينة بعد زيارة أخواله. ثم كفله جده عبد المطلب إلى أن توفي والنبي ﷺ في الثامنة من عمره، فانتقلت كفالته إلى عمه أبي طالب.",l:"عاش اليتم مبكرًا، فعرف معاناة الضعفاء وأوصى بهم طوال حياته."},
{i:"🐪",y:"٥٩٥م · ٢٥ سنة",t:"الزواج من خديجة",s:"تزوج خديجة بنت خويلد رضي الله عنها بعد رحلة تجارة إلى الشام.",d:"اشتهر بين قومه بالصادق الأمين، فاستأجرته خديجة للتجارة في مالها. وبعد عودته من الشام وما رأته من أمانته، تزوجها وكانت أول من آمن به، وأنجبت له أولاده ما عدا إبراهيم.",l:"الأمانة والصدق سبقا النبوة، فكانا سبب الثقة به قبل الرسالة."},
{i:"🕋",y:"٦٠٥م · ٣٥ سنة",t:"بناء الكعبة والحجر الأسود",s:"حكّمته قريش في خلافها على وضع الحجر الأسود فحلّ النزاع بحكمة.",d:"اختلفت قبائل قريش في من يضع الحجر الأسود في مكانه بعد تجديد بناء الكعبة، وكادت تقع حرب. فاتفقوا على تحكيم أول داخل عليهم فكان محمدًا ﷺ، فوضع الحجر في ثوب وأمر زعماء القبائل بحمله جميعًا، ثم وضعه بيده.",l:"الحكمة تحقن الدماء وتجمع الناس على كلمة واحدة."},
{era:1,t:"العهد المكي",s:"٦١٠م – ٦٢٢م"},
{i:"⛰️",y:"٦١٠م · ٤٠ سنة",t:"نزول الوحي في غار حراء",s:"نزل جبريل عليه السلام بأول آيات القرآن: ﴿اقرأ باسم ربك الذي خلق﴾.",d:"كان النبي ﷺ يتعبد في غار حراء، ففاجأه جبريل عليه السلام في شهر رمضان وأمره بالقراءة، ونزلت أول آيات سورة العلق. عاد إلى خديجة خائفًا فثبّتته، وذهبت به إلى ورقة بن نوفل الذي بشّره بأنه نبي هذه الأمة.",l:"أول كلمة نزلت كانت «اقرأ»، فبدأ الإسلام بالعلم."},
{i:"🕯️",y:"٦١٠م – ٦١٣م",t:"الدعوة السرية",s:"ثلاث سنوات من الدعوة الهادئة، وأول المؤمنين: خديجة وعلي وأبو بكر وزيد.",d:"بدأ النبي ﷺ دعوة المقربين سرًّا، فآمن خديجة وعلي بن أبي طالب وأبو بكر الصديق وزيد بن حارثة رضي الله عنهم. وأسلم على يد أبي بكر عدد من كبار الصحابة، وكان الصحابة يجتمعون في دار الأرقم بن أبي الأرقم.",l:"التدرج والتخطيط من سنن الدعوة الناجحة."},
{i:"📢",y:"٦١٣م",t:"الجهر بالدعوة",s:"صعد الصفا ونادى قريشًا، فبدأ الأذى والمواجهة.",d:"نزل قوله تعالى ﴿فاصدع بما تؤمر﴾ فصعد النبي ﷺ جبل الصفا ونادى قريشًا إلى التوحيد. فعارضه أبو لهب وجمهور قريش، وبدأ تعذيب المستضعفين مثل بلال وعمار وآل ياسر وخباب رضي الله عنهم.",l:"الثبات على الحق مع الأذى هو معيار صدق الدعوة."},
{i:"⛵",y:"٦١٥م",t:"الهجرة إلى الحبشة",s:"أمر النبي ﷺ جماعة من أصحابه بالهجرة إلى ملك عادل لا يُظلم عنده أحد.",d:"هاجر المسلمون مرتين إلى الحبشة، وكان على رأس الأولى عثمان بن عفان ومعه زوجته رقية. ولما أرسلت قريش وفدًا إلى النجاشي، تلا جعفر بن أبي طالب صدر سورة مريم فبكى النجاشي ورفض تسليمهم.",l:"حفظ الدين والنفس يجيز الانتقال إلى أرض الأمان."},
{i:"🏜️",y:"٦١٧م – ٦١٩م",t:"حصار شعب أبي طالب",s:"قاطعت قريش بني هاشم وبني المطلب نحو ثلاث سنوات.",d:"كتبت قريش صحيفة تقضي بمقاطعة بني هاشم وبني المطلب في البيع والشراء والزواج، فلجأ النبي ﷺ ومن معه إلى شعب أبي طالب. اشتد عليهم الجوع حتى أكلوا أوراق الشجر، ثم نُقضت الصحيفة بجهود نفر من قريش.",l:"الصبر الجماعي يكسر الحصار مهما طال."},
{i:"🥀",y:"٦١٩م · ١٠ للبعثة",t:"عام الحزن",s:"توفي أبو طالب ثم خديجة رضي الله عنها خلال أشهر قليلة.",d:"فقد النبي ﷺ عمه أبا طالب الذي كان يحميه، وبعده بقليل زوجته خديجة سنده الأول. فاشتد أذى قريش عليه، وسُمّي ذلك العام «عام الحزن».",l:"بعد الشدة يأتي الفرج، وما بعد هذا العام كان الإسراء والمعراج."},
{i:"🌄",y:"٦١٩م",t:"رحلة الطائف",s:"خرج يدعو أهل الطائف فردّوه وآذوه، فدعا بدعاء الاستضعاف.",d:"قصد النبي ﷺ الطائف ومعه زيد بن حارثة، فأعرضوا عنه وأغروا به سفهاءهم فرجموه حتى سالت قدماه الشريفتان. ولما عرض عليه ملَك الجبال أن يطبق عليهم الأخشبين قال: «بل أرجو أن يخرج الله من أصلابهم من يعبد الله وحده».",l:"الرحمة بالمخالف حتى في أشد لحظات الأذى."},
{i:"🌌",y:"٦٢١م",t:"الإسراء والمعراج",s:"رحلة من المسجد الحرام إلى المسجد الأقصى ثم إلى السماوات العلا.",d:"أُسري بالنبي ﷺ ليلًا من المسجد الحرام إلى المسجد الأقصى، ثم عُرج به إلى السماوات، وفُرضت الصلوات الخمس. وكانت تسلية له بعد عام الحزن، وتثبيتًا للمؤمنين، واختبارًا لإيمان الناس بخبره.",l:"الصلاة هدية السماء وصلة العبد بربه."},
{i:"🤝",y:"٦٢١م – ٦٢٢م",t:"بيعتا العقبة",s:"بايعه وفد من يثرب سرًّا عند العقبة على الإسلام ثم على النصرة.",d:"آمن ستة من الخزرج في موسم الحج، ثم جاء في العام التالي اثنا عشر رجلًا في العقبة الأولى، ثم نحو ثلاثة وسبعين رجلًا وامرأتين في العقبة الثانية بايعوا على حماية النبي ﷺ مما يحمون منه نساءهم وأبناءهم. وأرسل معهم مصعب بن عمير داعيًا ومعلمًا.",l:"الله يهيّئ الأسباب لمن صبر وأخلص."},
{era:2,t:"العهد المدني",s:"١هـ – ١١هـ (٦٢٢م – ٦٣٢م)"},
{i:"🌃",y:"٦٢٢م · ١هـ",t:"الهجرة إلى المدينة",s:"خرج النبي ﷺ مع أبي بكر مختفيًا، ومكثا في غار ثور ثلاثة أيام.",d:"أجمعت قريش على قتله، فنام علي رضي الله عنه في فراشه، وخرج النبي ﷺ مع أبي بكر إلى غار ثور، واستأجرا عبد الله بن أريقط دليلًا. وصلا قباء ثم المدينة، فاستقبلهم الأنصار بالفرحة والإنشاد. وبهذه الهجرة بدأ التقويم الهجري.",l:"الهجرة تخطيط وتوكل معًا: أخذٌ بالأسباب وثقةٌ بالله."},
{i:"🕌",y:"١هـ",t:"بناء المسجد والمؤاخاة ووثيقة المدينة",s:"أسس النبي ﷺ دولة على الإيمان والإخاء والعدل.",d:"بنى مسجده في المدينة، وآخى بين المهاجرين والأنصار، وكتب وثيقة تنظّم العلاقة بين المسلمين واليهود وسكان المدينة وتضمن الحقوق والواجبات.",l:"البناء يبدأ بالمسجد والأخوّة والقانون."},
{i:"⚔️",y:"٢هـ · ٦٢٤م",t:"غزوة بدر الكبرى",s:"في ١٧ رمضان انتصر نحو ٣١٣ مسلمًا على جيش قريش الذي يفوقهم عددًا.",d:"خرج المسلمون لاعتراض قافلة أبي سفيان، لكنها نجت وجاءت قريش بجيش يقارب ألفًا. وقعت المعركة عند آبار بدر وانتصر المسلمون، وقُتل عدد من زعماء قريش، وأُسر سبعون، فُدي بعضهم بتعليم أبناء المسلمين القراءة والكتابة.",l:"النصر من عند الله، والأخذ بالأسباب واجب."},
{i:"🛡️",y:"٣هـ · ٦٢٥م",t:"غزوة أحد",s:"تحول النصر إلى ابتلاء بعد مخالفة الرماة لأمر النبي ﷺ.",d:"انتصر المسلمون أولًا، ثم ترك معظم الرماة موقعهم على الجبل رغبةً في الغنيمة، فالتف خالد بن الوليد، وكان حينها مع قريش، وأصاب المسلمين خسائر. واستشهد حمزة بن عبد المطلب ومصعب بن عمير وسبعون من الصحابة، وجُرح النبي ﷺ.",l:"طاعة القيادة سر النجاح، والخطأ درس لا يهدم الثقة."},
{i:"⛏️",y:"٥هـ · ٦٢٧م",t:"غزوة الخندق",s:"حاصرت الأحزاب المدينة، وحفر المسلمون خندقًا بمشورة سلمان الفارسي.",d:"اجتمعت قريش وغطفان وحلفاؤهم في نحو عشرة آلاف، فحفر المسلمون خندقًا شمال المدينة. وبعد حصار نحو شهر أرسل الله ريحًا باردة شديدة أفسدت معسكر الأحزاب فانصرفوا.",l:"الشورى تأخذ بأفكار الجميع، وتأتي بما لا يُتوقع."},
{i:"📜",y:"٦هـ · ٦٢٨م",t:"صلح الحديبية",s:"ذهب النبي ﷺ معتمرًا فمنعته قريش، وانتهى الأمر بعقد صلح لعشر سنين.",d:"بدا الصلح في ظاهره قاسيًا على المسلمين، لكنه فتح باب الدعوة بالأمان، فدخل الناس في الإسلام أكثر من ذي قبل. ونزل في عودتهم قوله تعالى ﴿إنا فتحنا لك فتحًا مبينًا﴾.",l:"النظر بعيد المدى يجعل الصلح فتحًا."},
{i:"✉️",y:"٧هـ",t:"رسائل إلى الملوك",s:"أرسل النبي ﷺ رسائل تدعو ملوك العالم إلى الإسلام.",d:"كتب إلى هرقل ملك الروم وكسرى ملك فارس والمقوقس عظيم القبط والنجاشي وغيرهم. واتخذ لذلك خاتمًا نُقش عليه «محمد رسول الله». وكانت هذه الرسائل إعلانًا بأن الرسالة عالمية.",l:"رسالة الإسلام موجهة إلى الناس كافة."},
{i:"🕋",y:"٨هـ · ٦٣٠م",t:"فتح مكة",s:"دخل النبي ﷺ مكة في رمضان فاتحًا، وعفا عن أهلها: «اذهبوا فأنتم الطلقاء».",d:"بعد أن نقضت قريش صلح الحديبية، زحف النبي ﷺ بنحو عشرة آلاف، ودخل مكة بلا قتال يُذكر، وكسر الأصنام حول الكعبة. ووقف أمام قريش فقال لهم ما قال، فعمّ العفو. ثم كانت غزوة حنين في شوال من العام نفسه.",l:"العفو عند المقدرة أعظم من الانتقام."},
{i:"🐎",y:"٩هـ",t:"عام الوفود وغزوة تبوك",s:"توافدت القبائل على المدينة معلنة إسلامها.",d:"خرج النبي ﷺ في رجب إلى تبوك في جيش العسرة، ثم عاد وتتابعت الوفود من أنحاء الجزيرة، فسُمّي العام «عام الوفود». وأُمّر أبو بكر على الحج.",l:"حين تستقر الدولة تدخل القلوب إلى الإسلام أفواجًا."},
{i:"🏔️",y:"١٠هـ · ٦٣٢م",t:"حجة الوداع",s:"خطب في عرفة خطبته الجامعة بنحو مئة ألف من الصحابة.",d:"حج النبي ﷺ حجته الوحيدة وعلّم الناس مناسكهم، وأوصى بالنساء والعدل، وحرّم الدماء والأموال والأعراض، وقال «لعلي لا ألقاكم بعد عامي هذا». ونزل قوله تعالى ﴿اليوم أكملت لكم دينكم﴾.",l:"أوصى بحقوق الإنسان قبل أن يُعرف المصطلح بقرون."},
{i:"🌴",y:"١١هـ · ٦٣٢م · ٦٣ سنة",t:"وفاة النبي ﷺ",s:"انتقل إلى الرفيق الأعلى في المدينة يوم الاثنين من ربيع الأول.",d:"مرض أيامًا وأمر أبا بكر أن يصلي بالناس، وتوفي في بيت عائشة رضي الله عنها يوم الاثنين الثاني عشر من ربيع الأول سنة ١١هـ. ودُفن في حجرته، وهي اليوم في المسجد النبوي. وتولى أبو بكر الخلافة بعده.",l:"أدى الأمانة وبلّغ الرسالة، وبقيت سنّته نورًا للأمة."}
];
const tl=document.getElementById('tl'),evs=[];let cur=0;
const pic=e=>e.img?`<img src="${e.img}" alt="${e.t}" loading="lazy">`:e.i;
E.forEach(e=>{
 if(e.era!==undefined){const d=document.createElement('div');d.className='era';d.id='era'+e.era;d.innerHTML=`<h2>${e.t}</h2><span>${e.s}</span>`;tl.appendChild(d);return}
 const n=evs.length,d=document.createElement('div');d.className='ev '+(n%2?'R':'L');
 d.innerHTML=`<button class="card"><div class="pic">${pic(e)}</div><div class="yr">${e.y}</div><h3>${e.t}</h3><p>${e.s}</p><span class="more">اقرأ التفاصيل</span></button>`;
 d.querySelector('button').onclick=()=>openEv(n);tl.appendChild(d);evs.push(e);
});
const items=[...document.querySelectorAll('.ev')];
const io=new IntersectionObserver(es=>es.forEach(x=>{if(x.isIntersecting)x.target.classList.add('in')}),{threshold:.15});
items.forEach(el=>io.observe(el));
const bar=document.getElementById('bar'),fill=document.getElementById('fill');
function prog(){const h=document.documentElement.scrollHeight-innerHeight;bar.style.width=Math.min(1,scrollY/h)*100+'%';
 const r=tl.getBoundingClientRect();fill.style.height=Math.max(0,Math.min(r.height,innerHeight*.55-r.top))+'px';
 const eras=[...document.querySelectorAll('.era')];let a=-1;eras.forEach((x,i)=>{if(x.getBoundingClientRect().top<innerHeight*.5)a=i});
 document.querySelectorAll('nav button').forEach((b,i)=>b.classList.toggle('on',i===a))}
addEventListener('scroll',prog,{passive:true});prog();
document.querySelectorAll('nav button').forEach(b=>b.onclick=()=>document.getElementById(b.dataset.go).scrollIntoView());
const M=document.getElementById('modal');
function openEv(n){cur=n;const e=evs[n];mp.innerHTML=pic(e);my.textContent=e.y;mt.textContent=e.t;md.textContent=e.d;ml.textContent='العبرة: '+e.l;
 pv.style.visibility=n?'visible':'hidden';nx.style.visibility=n<evs.length-1?'visible':'hidden';M.classList.add('open');document.body.style.overflow='hidden';x.focus()}
function closeEv(){M.classList.remove('open');document.body.style.overflow='';items[cur]&&items[cur].scrollIntoView({block:'center'})}
x.onclick=closeEv;M.onclick=e=>{if(e.target===M)closeEv()};
nx.onclick=()=>openEv(cur+1);pv.onclick=()=>openEv(cur-1);
addEventListener('keydown',e=>{if(!M.classList.contains('open'))return;
 if(e.key==='Escape')closeEv();if(e.key==='ArrowLeft'&&cur<evs.length-1)openEv(cur+1);if(e.key==='ArrowRight'&&cur>0)openEv(cur-1)});
const c=document.getElementById('sky'),g=c.getContext('2d');let S=[];
function rs(){c.width=innerWidth;c.height=innerHeight;S=Array.from({length:Math.min(140,innerWidth/8)},()=>({x:Math.random()*c.width,y:Math.random()*c.height,r:Math.random()*1.6+.3,p:Math.random()*6,v:Math.random()*.02+.005}))}
rs();addEventListener('resize',rs);
(function f(t){g.clearRect(0,0,c.width,c.height);const off=scrollY*.08;
 S.forEach(s=>{g.globalAlpha=.35+.65*Math.abs(Math.sin(s.p+t*s.v*.1));g.fillStyle='#f2b83b';g.beginPath();g.arc(s.x,(s.y-off*s.r+c.height*3)%c.height,s.r,0,7);g.fill()});
 requestAnimationFrame(f)})(0);
</script>
</body>
</html>
