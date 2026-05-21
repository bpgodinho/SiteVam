<script>
    const carouselPhotos = [
		'/AboutPhotos/JAM_1.png',
		'/AboutPhotos/JAM_2.png',
		'/AboutPhotos/JAM_3.png',
        '/AboutPhotos/JAM_4.png',
        '/AboutPhotos/JAM_5.png',
        '/AboutPhotos/JAM_6.png',
        '/AboutPhotos/mostra_1.png',
        '/AboutPhotos/mostra_2.png',
        '/AboutPhotos/mostra_3.png',
        '/AboutPhotos/mostra_4.png',
        '/AboutPhotos/mostra_5.png',
        '/AboutPhotos/mostra_6.png',
        '/AboutPhotos/mostra_7.png',
        '/AboutPhotos/mostra_8.png',
        '/AboutPhotos/mostra_9.png',
        '/AboutPhotos/mostra_10.png',
        '/AboutPhotos/mostra_11.png',
        '/AboutPhotos/mostra_12.png',
        '/AboutPhotos/mostra_13.png',
        '/AboutPhotos/mostra_14.png'
	]
    
    const portraits = [
        "/Faculty/andre_carita 2.png",
        "/Faculty/andreia_pinto-de_sousa 2.png",
        "/Faculty/eduardo_magalhaes 2.png",
        "/Faculty/Felipe Coelho 1.png",
        "/Faculty/HenriqueBasto 1.png",
        "/Faculty/hugo_barbosa 2.png",
        "/Faculty/joao_alves_de_sousa 2.png",
        "/Faculty/jose_raimundo 2.png",
        "/Faculty/ricardo_mota 2.png",
        "/Faculty/rodrigo_carvalho 2.png",
        "/Faculty/vanessa_rodrigues 2.png",
    ];

    const facultyNames = [
        "André Carita",
        "Andreia Pinto-de-Sousa",
        "Eduardo Magalhães",
        "Felipe Coelho",
        "Henrique Basto",
        "Hugo Barbosa",
        "João Alves de Sousa",
        "José Raimundo",
        "Ricardo Mota",
        "Rodrigo Carvalho",
        "Vanessa Rodrigues"
    ];

    import {slide} from 'svelte/transition';

    import reference from '$lib/assets/Group 10.png'
    import pitch from '$lib/assets/Spaces/pitch0.png'
    import jam from '$lib/assets/Spaces/JAM_5.png'
    import mostra from '$lib/assets/Spaces/mostra_7.png'
    import discord from '$lib/assets/Spaces/discord.png'
    import partners from '$lib/assets/Spaces/partners.png'
	import logo from '$lib/assets/Logos/logo_VAM_no_txt.png'
    import logo_white from '$lib/assets/Logos/logo_VAM_white.png'
    import phone from '$lib/assets/Icons/PhoneIcon.png'
    import email from '$lib/assets/Icons/EmailIcon.png'

    let index = $state(0)
    let curSelected = $state(-1);
    let curScroll = 13;
    let scrolling = true;

	let container = $state(null);

    const ITEM_WIDTH = 308;

    const looped = $derived([
    ...portraits,
    ...portraits,
    ...portraits
    ]);

    function scrollNext(direction = true, multiply = 1) {
        curScroll = direction ? curScroll + multiply : curScroll - multiply;
        container?.scrollBy({
        left: direction ? ITEM_WIDTH * multiply : -ITEM_WIDTH * multiply,
        behavior: "smooth"
        });
    }

    function jumpScroll(left) {
        container.style.scrollBehavior = "auto";
        container.scrollLeft = left;

        requestAnimationFrame(() => {
        container.style.scrollBehavior = "smooth";
        });
    }

    function handleScroll() {
        if (!container) return;

        const sectionWidth = container.scrollWidth / 3;

        if (container.scrollLeft >= sectionWidth * 2) {
        jumpScroll(ITEM_WIDTH * (curScroll +1));
        }

        if (container.scrollLeft <= 0) {
        jumpScroll(ITEM_WIDTH * (curScroll +1));
        }
    }

    function tryScroll(direction = true, multiply = 1) {
        if (!scrolling) return;
        scrollNext(direction, multiply);
    }

    $effect(() => {
        const interval = setInterval(() => {
        index = (index + 1) % carouselPhotos.length;
        }, 3000);
        return () => clearInterval(interval);
    });

    $effect(() => {
        const interval = setInterval(() => tryScroll(true, 1), 3000);
        return () => clearInterval(interval);
    });

    $effect(() => {
        if (!container) return;

        requestAnimationFrame(() => {
        container.style.scrollBehavior = "auto";
        container.scrollLeft = container.scrollWidth / 3;

        requestAnimationFrame(() => {
            container.style.scrollBehavior = "smooth";
        });
        });
    });

    async function scrollClicked(idx) {
        scrolling = false;
        curSelected = idx;
        let totalScroll = idx - curScroll;
        if (idx < 3){
            console.log("there");
            container.style.scrollBehavior = "auto";
            container.scrollLeft = (container.scrollWidth / 3) - (ITEM_WIDTH * (totalScroll));
            curScroll = 14 + (totalScroll);
            curSelected = 14 + (totalScroll);
            await new Promise(resolve => setTimeout(resolve, 5));
            container.style.scrollBehavior = "smooth";
            container.scrollLeft = ITEM_WIDTH * (curScroll - 2);
            return;
        }
        if (idx >= 24){
            console.log("here");
            container.style.scrollBehavior = "auto";
            container.scrollLeft = (container.scrollWidth / 3) - (ITEM_WIDTH * (totalScroll));
            curScroll = 12 + (totalScroll);
            curSelected = 12 + (totalScroll);
            await new Promise(resolve => setTimeout(resolve, 5));
            container.style.scrollBehavior = "smooth";
            container.scrollLeft = ITEM_WIDTH * (curScroll-2);
            return;
        }
        scrollNext(totalScroll > 0, Math.abs(totalScroll));
    }
</script>

<style>
:global(body) {margin: 0px; padding: 0px; overflow-x: hidden;background-color: #292929;}

.reference{position: absolute; width: 100%;z-index: -99;}
.top-nav{position: fixed; display:flex; height: 65px; width:100%; background-color:#4d4c4c;z-index: 1;}
.vam-logo{max-height: 100%; height:auto; padding: 0.75%; padding-left: 3%;}
.nav-list{position: absolute; display:flex; justify-content: center; align-items: center; width: 100%; height: 100%; margin: 0%; padding: 0%;}
.top-nav-item{font-family: "Outfit", sans-serif;font-size: x-large; font-weight: 200; color: white;padding-left: 0%;text-decoration:none;}
.selected-top-nav-item{font-family: "Outfit", sans-serif;font-size: x-large; font-weight: 200; color: #23d400;padding-left: 0%;}
.vertical{margin: 10px;border-left: 2px solid white;height: 20px; }

.about-carousel{width:100%;z-index: -1;}
.carousel-container{display: flex; justify-content: center;align-items: center;width: 100%;position: relative; padding-top: 65px;}
.carousel-control{width: 5%; cursor: pointer;}

.links-about{display: flex; justify-content: center; align-items: center; display: flex; flex-direction: column; padding-top: 4%; z-index: 1;
     color: white; font-family: "Outfit", sans-serif; font-size: 10.5vmin; text-shadow: 0px 0px 12px #23d400;}
.about-description{position:relative;border-radius: 20px;background-color: #1a1a1a; font-size: 2.7vmin; color: white;
    font-family: "Outfit", sans-serif; width: 75%; padding: 3%; box-shadow: 0px 0px 20px 20px #2582135c; -webkit-text-stroke: 0.04vmin #23d400; line-height: 1.5;
    margin-top: 4%; border: 0.1vmin solid #23d400; text-shadow: 0px 0px 0px rgba(255, 255, 255, 0)}

.course-spaces{display: flex; flex-direction: column; justify-content: center; align-items: center; width: 100%; margin-top: 10%;}
.space-show{position: relative; display: flex; justify-content: center; width: 75%; padding: 3%;
    border-radius: 20px; background-color: #1a1a1a; box-shadow: 0px 0px 20px 20px #2582135c; border: 0.1vmin solid #23d400; margin-bottom: 10%;}
.space-text{flex-direction: column; width: 50%; color: white; font-family: "Outfit", sans-serif; margin-right: 5%;}
.space-title{font-size: 5vmin; font-weight: bold;}
.space-description{font-size: 2.7vmin; text-shadow: 0px 0px 0px rgba(255, 255, 255, 0); -webkit-text-stroke: 0.04vmin #23d400;line-height: 1.5;text-justify: center;
    height: 90%; display: flex; align-items: center;}
.space-show-img{border-radius: 20px;}

.faculty{display: flex; flex-direction: column; justify-content: center; align-items: center; width: 100%; color: white;
    font-family: "Outfit", sans-serif; font-size: 10.5vmin; text-shadow: 0px 0px 12px #23d400; margin-bottom: 5%;}
.faculty-description{font-size: 2.7vmin; color: white;
    font-family: "Outfit", sans-serif; width: 75%; padding: 3%; box-shadow: 0px 0px 20px 20px #2582135c; -webkit-text-stroke: 0.04vmin #23d400; line-height: 1.5;
    margin-top: 4%; border: 0.1vmin solid #23d400; text-shadow: 0px 0px 0px rgba(255, 255, 255, 0); text-align: center; border-radius: 20px;}
.wrapper {position: relative; display: block; align-items: center; gap: 12px; width: 100%;margin-top: 5%;}
.portrait-strip {display: flex;gap: 8px;overflow-x: auto;scroll-behavior: smooth;scrollbar-width: none;overflow-y: visible;width: 100%;padding: 40px;}
.portrait-strip::-webkit-scrollbar {display: none;}
.portrait {width: 300px;height: 370px;border-radius: 27px;user-select: none;}
.portrait:hover {transform: scale(1.05); transition: transform 0.3s ease-in-out;}
.professor-profile{display: flex; align-items: center; width: 70%; height: 100%;
    background-color: #1a1a1a; border-radius: 20px; box-shadow: 0px 0px 20px 20px #2582135c; border: 0.1vmin solid #23d400;left: 50%; top: 50%; transform: translate(25%, -105%); z-index: 10;}
.professor-name{font-size: 3vmin; color: white; text-shadow: 0px 0px 0px rgba(255, 255, 255, 0); -webkit-text-stroke: 0.04vmin #23d400;}
.profile-portrait{width: 30%; height: 90%; border-radius: 20px; margin-left: 2.5%; margin-right: 5%; max-height:none;}

.footer-div{background-color:#2d7328; height: 70px; display: flex; bottom: 0px;}
.contact-logo{max-height: 100%; height:auto; padding: 0.75%; padding-left: 3%;}
.contact-div{align-content: center; font-family: "Outfit", sans-serif;font-size: 2.5vmin;
    margin-left: 2%;color: white;height: 70px;display: flex;align-items: center;width: 45%;}
.phone-ico{max-height: 40%;margin-left: 5%; margin-right: 1%;}

</style>

<!-- <img src={reference} class="reference"> -->
<nav class="top-nav">
    <img class="vam-logo" alt="Vam Logo" src={logo}>
    <ul class="nav-list">
        <a class="top-nav-item" href="/">
            HOME
        </a>
        <div class= "vertical"></div>
        <div class="selected-top-nav-item">
            SOBRE
        </div>
        <div class= "vertical"></div>
        <a class="top-nav-item" href="/games">
            JOGOS
        </a>
        <div class= "vertical"></div>
        <a class="top-nav-item" href="/articles">
            ARTIGOS
        </a>
    </ul>
</nav>
<div class="carousel-container">
    <img src={carouselPhotos[index]} class="about-carousel">
</div>
<div class="links-about">
    Sobre Nós
    <div class="about-description">
        VAM é uma Licenciatura com uma componente prática intensa que te prepara para o mercado de trabalho. Não sabes se gostarias de seguir o campo da programação, da arte, sonoplastia ou game design?<br>
        Estás no local certo, pois terás a oportunidade de aprender e experimentar todas essas áreas tendo uma visão abrangente dos principais processos e trabalhos no campo do desenvolvimento de Videojogos e Aplicações Multimédia. Os projetos de grupo que desenvolvemos permitirão que te especializes nas áreas que demonstres mais capacidades, desta forma, a formação de cada estudante é personalizada e em cada turma são desenvolvidos perfis distintos.<br>
        As várias disciplinas do curso funcionam em grande interligação e sentirás que estás sempre a trabalhar em pequenas partes de projetos maiores.<br>
    </div>
    <div class="course-spaces">
        <div class="space-show">
            <div class="space-text">
                <div class="space-title">
                    PITCH VAM
                </div>
                <div class="space-description">
                    Tens dificuldade em falar em público? Vamos ajudar-te a superar isso!<br>
                    As apresentações de trabalhos são um ponto importante do nosso curso e todos os estudantes aprenderão como apresentar as suas ideias da melhor forma. Os projetos são escolhidos pelo mérito, criatividade e exequibilidade de cada proposta apresentada e votados entre professores e estudantes.
                </div>
            </div>
            <img src={pitch} class="space-show-img">
        </div>
        <div class="space-show">
            <div class="space-text">
                <div class="space-title">
                    VAM GAME JAM
                </div>
                <div class="space-description">
                    Durante 48 horas, criatividade e paixão juntam-se num fim de semana inesquecível. Como JAM Site oficial da Global Game Jam, recebemos criadores de videojogos para desenvolver projetos intensivos cheios de convívio, pizza e inovação.
                </div>
            </div>
            <img src={jam} class="space-show-img">
        </div>
        <div class="space-show">
            <div class="space-text">
                <div class="space-title">
                    MOSTRA VAM
                </div>
                <div class="space-description">
                    O momento em que os projetos ganham vida perante o público.<br>
                    Testa os jogos, recebe feedback e participa numa celebração criativa onde são escolhidos os melhores projetos do ano em várias categorias.
                </div>
            </div>
            <img src={mostra} class="space-show-img">
        </div>
        <div class="space-show">
            <div class="space-text">
                <div class="space-title">
                    DISCORD VAM
                </div>
                <div class="space-description">
                    Uma comunidade ativa onde estudantes, licenciados, professores e profissionais interagem diariamente.<br>
                    Partilha trabalhos, tira dúvidas, encontra oportunidades e conversa sobre jogos, filmes, anime, cultura geek e muito mais.
                </div>
            </div>
            <img src={discord} class="space-show-img">
        </div>
    </div>
    <div class="space-show">
            <div class="space-text">
                <div class="space-title">
                    PARCEIROS
                </div>
                <div class="space-description">
                    Ao longo dos anos, vamos tendo a oportunidade de trabalhar com diversas empresas da área de desenvolvimento de Videojogos e Aplicações Multimédia, sobretudo como parceiros de estágios curriculares. 
                    Destacamos algumas:
                </div>
            </div>
            <img src={partners} class="space-show-img">
        </div>
</div>

<div class="faculty">
    Docentes
    <div class="faculty-description">
        A nossa equipa de docentes é composta por profissionais experientes e apaixonados, dedicados a fornecer uma educação de alta qualidade e a apoiar o desenvolvimento dos nossos estudantes. Com uma vasta experiência na indústria de videojogos e multimédia, os nossos professores trazem uma perspectiva prática e atualizada para as suas aulas, preparando os alunos para os desafios do mercado de trabalho.
    </div>
    <div class="wrapper">
        <div bind:this={container} class="portrait-strip" onscroll={handleScroll}>
        {#each looped as src, i}
        <img src={src} alt={`Portrait ${i}`} class="portrait" draggable="false" style="filter: grayscale({curSelected === i ? 0 : 100}%);" onclick={() => scrollClicked(i)}/>
        {/each}
        </div>
        {#if curSelected >= 0}
        <div class="professor-profile" transition:slide>
            <img src={portraits[curSelected % portraits.length]} alt={`Portrait ${curSelected}`} class="profile-portrait">
            <div class="professor-name">
                {facultyNames[curSelected % portraits.length]}
            </div>
        </div>
        {/if}
    </div>
    
</div>
<div class="footer-div">
    <img src={logo_white} class="contact-logo">
    <div class="contact-div">
        <div>
            Contactos:
        </div>
        <img src={phone} class="phone-ico">
        Tel: 999 999 999
        <img src={email} class="phone-ico">
        Mail: example@gmail.com
    </div>
</div>
