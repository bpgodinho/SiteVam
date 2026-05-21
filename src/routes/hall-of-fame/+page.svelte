<script>
	import logo_no_txt from '$lib/assets/Logos/logo_VAM_no_txt.png'
    import logo_white from '$lib/assets/Logos/logo_VAM_white.png'
    import phone from '$lib/assets/Icons/PhoneIcon.png'
    import email from '$lib/assets/Icons/EmailIcon.png'

    const posters = [
        '/Posters/poster (1).png',
        '/Posters/poster (2).png',
        '/Posters/poster (3).png',
        '/Posters/poster (4).png',
        '/Posters/poster (5).png',
        '/Posters/poster (6).png',
        '/Posters/poster (7).png',
        '/Posters/poster (8).png',
        '/Posters/poster (9).png',
        '/Posters/poster (10).png',
        '/Posters/poster (11).png',
        '/Posters/poster (12).png',
        '/Posters/poster (13).png',
        '/Posters/poster (14).png',
        '/Posters/poster (15).png',
        '/Posters/poster (16).png',
        '/Posters/poster (17).png',
        '/Posters/poster (18).png'
    ];

    const ilustracoes = [
        '/Ilustracao/ilustracao (1).jpeg',
        '/Ilustracao/ilustracao (1).jpg',
        '/Ilustracao/ilustracao (1).png',
        '/Ilustracao/ilustracao (2).jpg',
        '/Ilustracao/ilustracao (2).png',
        '/Ilustracao/ilustracao (3).jpg',
        '/Ilustracao/ilustracao (3).png',
        '/Ilustracao/ilustracao (4).jpg',
        '/Ilustracao/ilustracao (4).png',
        '/Ilustracao/ilustracao (5).jpg',
        '/Ilustracao/ilustracao (5).png',
        '/Ilustracao/ilustracao (6).jpg',
        '/Ilustracao/ilustracao (6).png',
        '/Ilustracao/ilustracao (7).jpg',
        '/Ilustracao/ilustracao (7).png',
        '/Ilustracao/ilustracao (8).jpg',
        '/Ilustracao/ilustracao (8).png',
        '/Ilustracao/ilustracao (9).jpg',
        '/Ilustracao/ilustracao (9).png',
        '/Ilustracao/ilustracao (10).jpg',
        '/Ilustracao/ilustracao (10).png',
        '/Ilustracao/ilustracao (11).jpg',
        '/Ilustracao/ilustracao (11).png',
        '/Ilustracao/ilustracao (12).jpg',
        '/Ilustracao/ilustracao (12).png',
        '/Ilustracao/ilustracao (13).jpg',
        '/Ilustracao/ilustracao (13).png',
        '/Ilustracao/ilustracao (14).jpg',
        '/Ilustracao/ilustracao (14).png',
        '/Ilustracao/ilustracao (15).jpg',
        '/Ilustracao/ilustracao (15).png',
        '/Ilustracao/ilustracao (16).jpg',
        '/Ilustracao/ilustracao (16).png',
        '/Ilustracao/ilustracao (17).jpg',
        '/Ilustracao/ilustracao (17).png',
        '/Ilustracao/ilustracao (18).jpg',
        '/Ilustracao/ilustracao (18).png',
        '/Ilustracao/ilustracao (19).jpg',
        '/Ilustracao/ilustracao (19).png',
        '/Ilustracao/ilustracao (20).jpg',
        '/Ilustracao/ilustracao (20).png',
    ]

    const looped_ilustracoes = $derived([
        ...ilustracoes,
        ...ilustracoes
    ])

    const looped_posters = $derived([
    ...posters,
    ...posters,
    ]);

    const scrollAmount = 1;

    let poster_container = $state(null);
    let ilustracao_container = $state(null);

    function getWidth() {
        return document.documentElement.clientWidth / 4;
    }

    async function scrollTick() {
        if (poster_container.scrollLeft >= getWidth() * (posters.length)) {
            poster_container.scrollLeft = 0;
            await new Promise(resolve => setTimeout(resolve, 250));
            poster_container.style.scrollBehavior = "smooth";
        } else {
            poster_container.scrollLeft += scrollAmount;
        }
    }

    $effect(() => {
        const interval = setInterval(() => scrollTick(), 10);
        return () => clearInterval(interval);
    });

</script>

<style>
:global(body) {margin: 0px; padding: 0px; overflow-x: hidden;background-color: #292929;}

.reference{position: absolute; width: 100%;z-index: -99;}
.top-nav{position: fixed; display:flex; height: 65px; width:100%; background-color:#232323;z-index: 999;}
.vam-logo{max-height: 100%; height:auto; padding: 0.75%; padding-left: 3%;}
.nav-list{position: absolute; display:flex; justify-content: center; align-items: center; width: 100%; height: 100%; margin: 0%; padding: 0%;}
.top-nav-item{font-family: "Outfit", sans-serif;font-size: x-large; font-weight: 200; color: white;padding-left: 0%;text-decoration:none;}
.selected-top-nav-item{font-family: "Outfit", sans-serif;font-size: x-large; font-weight: 200; color: #23d400;padding-left: 0%;}
.vertical{margin: 10px;border-left: 2px solid white;height: 20px; }

.title{display: flex; font-family: "Outfit", sans-serif;font-size: 10vmin; font-weight: bold; color: white;text-align: center;justify-self: center;
    padding-top: 100px;padding-bottom: 1%;text-shadow: 0px 0px 10px #23d400;margin-bottom: 5%;}

.category-info{display: flex; width:100%; flex-direction: column; padding: 2%; justify-content: center; align-items: center;background-color: black; border:#23d400 0.1vmin solid;}
.category-title{font-family: "Outfit", sans-serif;font-size: 5vmin; font-weight: bold; color: white;text-align: center;text-shadow: 0px 0px 10px #23d400;}
.category-description{font-family: "Outfit", sans-serif;font-size: 2.5vmin; font-weight: 200; color: white;text-align: center;padding-top: 1%;-webkit-text-stroke: 0.03vmin #23d400;}
.carousel-imgs{position: relative; display: flex; flex-direction: row; width: 100%; overflow-x:scroll;scroll-behavior: smooth;scrollbar-width: none;}

.footer-div{background-color:#2d7328; height: 70px; display: flex; bottom: 0px;}
.contact-logo{max-height: 100%; height:auto; padding: 0.75%; padding-left: 3%;}
.contact-div{align-content: center; font-family: "Outfit", sans-serif;font-size: 2vmin; margin-left: 2%;color: white;height: 70px;display: flex;align-items: center;width: 45%;}
.phone-ico{max-height: 40%;margin-left: 5%; margin-right: 1%;}
</style>

<nav class="top-nav">
    <img class="vam-logo" alt="Vam Logo" src={logo_no_txt}>
    <ul class="nav-list">
        <a class="top-nav-item" href="/">
            HOME
        </a>
        <div class= "vertical"></div>
        <a class="top-nav-item" href="/about">
            SOBRE
        </a>
        <div class= "vertical"></div>
        <a class="top-nav-item" href="/curriculum">
            PLANO
        </a>
        <div class= "vertical"></div>
        <div class="selected-top-nav-item">
            HALL OF FAME
        </div>
    </ul>
</nav>

<div class="title">
    VAM Hall of Fame
</div>
<div class="category-div">
    <div class="category-info">
        <div class="category-title">Jogos</div>
        <div class="category-description">Assiste aos trailers dos jogos desenvolvidos pelos nossos estudantes</div>
    </div>
    <img class="category-image" style="width: 10%;">
</div>
<div class="category-div">
    <div class="category-info">
        <div class="category-title">Posters</div>
        <div class="category-description">Galeria de posters criados pelos nossos estudantes para os seus jogos preferidos e também para os seus próprios projetos!</div>
    </div>
    <div class="carousel-imgs" bind:this={poster_container}>
        {#each looped_posters as src, i}
            <img src={src} alt={`Portrait ${i}`} class="poster" draggable="false" style=";width: 25%;"/>
        {/each}
    </div>
</div>
<div class="category-div">
    <div class="category-info">
        <div class="category-title">Posters</div>
        <div class="category-description">Galeria de posters criados pelos nossos estudantes para os seus jogos preferidos e também para os seus próprios projetos!</div>
    </div>
    <div class="carousel-imgs" bind:this={ilustracao_container}>
        {#each looped_ilustracoes as src, i}
            <img src={src} alt={`Portrait ${i}`} class="poster" draggable="false" style=";width: 25%;"/>
        {/each}
    </div>
</div>
<div class="footer-div">
    <img src={logo_white} class="contact-logo">
    <div class="contact-div">
        <img src={phone} class="phone-ico">
        Tel: 222 073 230
        <img src={email} class="phone-ico">
        Mail: info.cup@ulusofona.pt
        joao.alves.de.sousa@ulusofona.pt 
    </div>
</div>
