<script>
    const carouselPhotos = [
		'/AboutPhotos/JAM_1.png',
		'/AboutPhotos/JAM_2.png',
		'/AboutPhotos/JAM_3.png',
        '/AboutPhotos/JAM_4.png',
        '/AboutPhotos/JAM_6.png',
        '/AboutPhotos/mostra_1.png',
        '/AboutPhotos/mostra_2.png',
        '/AboutPhotos/mostra_3.png',
        '/AboutPhotos/mostra_4.png',
        '/AboutPhotos/mostra_5.png',
        '/AboutPhotos/mostra_6.png',
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

    const professorBio = [
        "Subdiretor do Curso - Especialista em História, Teoria e Game Design <br>Criações em destaque: <br> - Autor do livro A Fotografia nos Videojogos - Um ensaio Fotográfico ao The Last of Us Part II (2023) <br>- Coautor do livro A Visão Crítica do Estudante: Videojogos Independentes (2023) <br>- Autor do livro Pensar Videojogos: Design, Arte e Comunicação (2015) <br>- Coautor do livro A Visão Crítica do Estudante: Videojogos Independentes (2023) <br>- Autor do livro Pensar Videojogos: Design, Arte e Comunicação (2015)",
        "",
        "Docente e Investigador - Especialista em Sonoplastia e Tecnologias Multimédia <br>Criações em Destaque:<br>- Oktoberfest VR (Vencedor dos AUREA AWARDS 2026 na categoria de imersão)<br>- Oktoberfest VR  (Finalista dos XR Awards - AIXR 2026 na categoria de melhor jogo do ano)<br>- Beneath (Nomeação notável para Jogo do Ano nos Spotlight Awards 2025 e destaque nos Horror Game Awards 2025.",
        "Especialista em programação e motores de jogo<br>Criações em Destaque:<br>- Flat Fat Fartfest  3D Platformer, PC, 2024<br>- Whatta Frogs Social Multiplayer, PC, 2026 <a href='https://store.steampowered.com/app/3762800/Whatta_Frogs/' style='text-decoration:none;color:white'>https://store.steampowered.com/app/3762800/Whatta_Frogs/</a><br>- Mirage Blocks Puzzle, Mobile, 2023",
        "Especialista em programação e motores de jogo<br>Criações em Destaque:<br>",
        "Especialista em tecnologias multimédia e Web<br>Criações em Destaque:<br>",
        "Diretor do Curso - Doutorado em Arte Interativa, Especialista em Imagem Digital, Game Design e Animação. <br>Criações em destaque: <br>- Free that Fish (videojogo apresentado na Comic Con Portugal, Lisbon Games Week e The Very Big Indie Pitch - Pocket Gamer Connects London, 2015)<br>- Lots of Guts (Vencedor de Jogo mais Inovador Prémios Playstation Portugal 2015)<br>- Porquê (Animação Vencedora do Prémio de Jovem Cineasta Português - Cinanima 2006)",
        "Doutorado em Medias Digitais - Especialista em ilustração e 3D.<br>Criações em destaque:<br>- Coordenador do projecto internacional Virtual Production Studio Networks <br>- The case of See, Hear, Touch no Evil e Bully Who?. Jogos de tabuleiro/digital (DIGICOM 2018 e 2019). <br>- Segundo lugar na 4º Competição Internacional de Ilustração, Treviso, Itália. (2016)",
        "Especialista em Design, Produção, Gestão de Equipas e Marketing para jogos<br>Criações em destaque:<br>- Communications & Studio Manager na Krafton (PUBG Studios)<br>- Thunder Tier One, PUBG Plack Budget<br>- Cofundador do Festival de jogos Indie X, Editor Rubber Chicken Games",
        "Doutorado em Medias Digitais - Especialista em Arte Digital e Motion Graphics<br>Criações em destaque:<br>- 30xN - Performance Audiovisual (SÓNAR, Istambul; GNRATION, Braga; SERRALVES, Porto; CONVENTO SÃO FRANCISCO, Coimbra; 2024-2026)<br>- Vanishing Quasars - Performance Audiovisual (ELECTROALTERNATIVE, Toulouse); FOTONICA, Roma; CRIATECH, Aveiro; 948MERKABA, Pamplona; MAPPING FESTIVAL, Genebra; VOLUMENS DAY, Valencia; SÓNAR, Lisboa; 2019-2023)<br>- Multiverse - Performance Audiovisual  (SÓNAR, Barcelona; BAM, Liège; STEREOLUX, Nantes; ADAF, Atenas; ECHO, Dubai; BRIGHTBRUSSELS, Bruxelas; 2016-2019)",
        "Vanessa Rodrigues - Especialista em Produção Audiovisual <br>Criações em Destaque:<br>- Realizadora e Argumentista: O Feitiço de Areia (82', Portugal/Moçambique, 2025), filme documental: em distribuição  (2026)<br>- Realizadora, Produtora e Argumentista: Baptismo de Terra (90', Portugal/Brasil, 2015), filme documental (Menção Especial no Festival de Cinema de Avanca, 2017; Prémio Terres/Espanha de melhor banda sonora, 2018; Prémio Melhor Cinematografia - Hollywood Women's Film Festival, 2019)<br>- Realizadora e Argumentista: Palestina, Diários de um lugar incerto (37', Cisjordânia/Jordânia, 2013), áudio-documentário TSF (Menção Honrosa, Prémio UNESCO- Jornalismo, Integração & Direitos Humanos)",
    ];

    import {slide} from 'svelte/transition';
    import { innerWidth, innerHeight } from 'svelte/reactivity/window'

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
    import closeBtn from '$lib/assets/Icons/CloseIcon.png'

    let index = $state(0)
    let curSelected = $state(-1);
    let curScroll = 13;
    let scrolling = true;

	let container = $state(null);

    function getWidth() {
        return document.documentElement.clientWidth / 5;
    }

    const looped = $derived([
    ...portraits,
    ...portraits,
    ...portraits
    ]);

    function scrollNext(direction = true, multiply = 1) {
        curScroll = direction ? curScroll + multiply : curScroll - multiply;
        container?.scrollBy({
        left: direction ? (getWidth()) * multiply : -(getWidth()) * multiply,
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
        jumpScroll((innerWidth / 5) * (curScroll +1));
        }

        if (container.scrollLeft <= 0) {
        jumpScroll((innerWidth / 5) * (curScroll +1));
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
            curScroll = 13;
            container.style.scrollBehavior = "auto";
            container.scrollLeft = container.scrollWidth / 3;

            requestAnimationFrame(() => {
                container.style.scrollBehavior = "smooth";
            });
        });
    });

    async function scrollClicked(idx) {
        console.log();
        scrolling = false;
        curSelected = idx;
        let totalScroll = idx - curScroll;
        if (idx < 3){
            console.log("there");
            container.style.scrollBehavior = "auto";
            container.scrollLeft = (container.scrollWidth / 3) - ((getWidth()) * (totalScroll));
            curScroll = 14 + (totalScroll);
            curSelected = 14 + (totalScroll);
            await new Promise(resolve => setTimeout(resolve, 5));
            container.style.scrollBehavior = "smooth";
            container.scrollLeft = (getWidth()) * (curScroll - 2);
            return;
        }
        if (idx >= 24){
            console.log("here");
            container.style.scrollBehavior = "auto";
            container.scrollLeft = (container.scrollWidth / 3) - ((getWidth()) * (totalScroll));
            curScroll = 12 + (totalScroll);
            curSelected = 12 + (totalScroll);
            await new Promise(resolve => setTimeout(resolve, 5));
            container.style.scrollBehavior = "smooth";
            container.scrollLeft = (getWidth())  * (curScroll-2);
            return;
        }
        scrollNext(totalScroll > 0, Math.abs(totalScroll));
    }
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
.space-show-img{border-radius: 20px;width: 45%; height: 90%; object-fit: cover;align-self: center;}

.faculty{display: flex; flex-direction: column; justify-content: center; align-items: center; width: 100%; color: white;
    font-family: "Outfit", sans-serif; font-size: 10.5vmin; text-shadow: 0px 0px 12px #23d400; margin-bottom: 10%;}
.faculty-description{font-size: 2.7vmin; color: white;
    font-family: "Outfit", sans-serif; width: 75%; padding: 3%; box-shadow: 0px 0px 20px 20px #2582135c; -webkit-text-stroke: 0.04vmin #23d400; line-height: 1.5;
    margin-top: 4%; border: 0.1vmin solid #23d400; text-shadow: 0px 0px 0px rgba(255, 255, 255, 0); text-align: center; border-radius: 20px;}
.wrapper {position: relative; display: block; align-items: center; gap: 12px; width: 100%;margin-top: 5%;}
.portrait-strip {display: flex;gap: 8px;overflow-x: auto;scroll-behavior: smooth;scrollbar-width: none;overflow-y: visible;width: 100%;padding: 40px;}
.portrait-strip::-webkit-scrollbar {display: none;}
.portrait {width: 20%;height: 370px;border-radius: 27px;user-select: none;}
.portrait:hover {transform: scale(1.05); transition: transform 0.3s ease-in-out;}

.professor-profile{position:absolute; display: flex; align-items: center; width: 70%; height: 100%;
    background-color: #1a1a1a; border-radius: 20px; box-shadow: 0px 0px 20px 20px #2582135c; border: 0.1vmin solid #23d400;
    left: 50%; top: 50%; transform: translate(-50%, -50%); z-index: 0;}
.professor-name{font-size: 5vmin; color: white; text-shadow: 0px 0px 0px rgba(255, 255, 255, 0); text-shadow: 0px 0px 12px #23d400; font-weight: bold;}
.profile-portrait{width: 30%; height: 90%; border-radius: 20px; margin-left: 2.5%; margin-right: 5%; max-height:none;object-fit:cover;}
.professor-bio-container{display: flex; flex-direction: column; gap: 2%; height: 100%; width: 65%; padding-right: 5%; margin-top: 10%;margin-bottom: 5%;}
.professor-description{font-size: 2.5vmin; color: white; text-shadow: 0px 0px 0px rgba(255, 255, 255, 0); -webkit-text-stroke: 0.04vmin #23d400;line-height: 1.5;text-justify: center;
    height: 90%;margin-top: 10%;overflow-y: auto;margin-bottom: 10%;scrollbar-color: #23d400, #1a1a1a;}

.professor-description::-webkit-scrollbar {width: 5px; height: auto;}
.professor-description::-webkit-scrollbar-thumb {background-color: #23d400; border-radius: 10px;}
.professor-description::-webkit-scrollbar-track {background-color: #1a1a1a; border-radius: 10px;}
.close-btn{position: absolute; width: 2%; top: 5%; right: 2%; cursor: pointer;}

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
        <a class="top-nav-item" href="/curriculum">
            PLANO
        </a>
        <div class= "vertical"></div>
        <a class="top-nav-item" href="/hall-of-fame">
            HALL OF FAME
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
            <div class="professor-bio-container">
                <div class="professor-name">
                    {facultyNames[curSelected % portraits.length]}
                </div>
                <div class="professor-description">
                    {@html professorBio[curSelected % portraits.length]}
                </div>
            </div>
            <img src={closeBtn} class="close-btn" onclick={() => (curSelected = -1,scrolling = true)}/>
        </div>
        {/if}
    </div>
    
</div>
<div class="footer-div">
    <img src={logo_white} class="contact-logo">
    <div class="contact-div">
        <img src={phone} class="phone-ico">
        Tel: 222 073 230
        <img src={email} class="phone-ico">
        info.cup@ulusofona.pt
        joao.alves.de.sousa@ulusofona.pt 
    </div>
</div>
