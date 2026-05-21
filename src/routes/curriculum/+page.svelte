<script>
    import {slide} from 'svelte/transition';

	import logo_no_txt from '$lib/assets/Logos/logo_VAM_no_txt.png'
    import logo_white from '$lib/assets/Logos/logo_VAM_white.png'
    import phone from '$lib/assets/Icons/PhoneIcon.webp'
    import email from '$lib/assets/Icons/EmailIcon.png'
    import facebookIco from '$lib/assets/Icons/fbIcon.png'
    import instagramIco from '$lib/assets/Icons/InstagramIcon.png'
    import youtubeIco from '$lib/assets/Icons/ytIcon.png'
    import logoULP from '$lib/assets/Logos/logo_ULP.png'

    let panels = $state([
        false,
        false,
        false,
        false,
        false,
        false
    ])

function togglePanel(idx) {
    panels[idx] = !panels[idx];
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
.padding-div{padding-top: 65px;}

.title{display: flex; font-family: "Outfit", sans-serif;font-size: 8vmin; font-weight: bold; color: white;text-align: center;justify-self: center;
padding-top: 1%;padding-bottom: 1%; text-shadow: 0px 0px 10px #23d400;}

.level-div{display: flex; flex-direction: column; gap: 5%; padding: 2%;justify-content: start; align-items: flex-start;}
.level-title{font-family: "Outfit", sans-serif;font-size: 4vmin; font-weight: bold; color: white;background-color: #1a1a1a; padding: 1%;
    border-radius: 2vmin; box-shadow: 0px 0px 40px 10px #2582135c;border: 0.1vmin solid #23d400;}
.semester-container{display: flex; gap: 5%; justify-content: center; align-items: start; width: 100%;}
.semester-card{position: relative; width: 100%;}
.semester-title{font-family: "Outfit", sans-serif;font-size: 5vmin; font-weight: bold; color: white;text-align: center;background-color: black;
    padding: 5%; border-radius: 2vmin;border: 0.1vmin solid #23d400; margin-top: 10%;z-index: 2; cursor: pointer;}

.semester-description{position:relative; font-family: "Outfit", sans-serif;font-size: 2.5vmin; color: white; padding: 5%; background-color: #1a1a1a; border-radius: 2vmin;
    border: 0.1vmin solid #23d400; margin-top: -15%;z-index: -1;padding-top: 20%;}

.footer-div{background-color:#2d7328; height: 70px; display: flex; bottom: 0px;}
.contact-div{align-content: center; font-family: "Outfit", sans-serif;font-size: 1vw; margin-left: 0%;color: white;height: 70px;display: flex;align-items: center;width: 45%;}
.phone-ico{max-height: 40%;margin-left: 5%; margin-right: 1%;}
.socials{display: flex; justify-content: center; align-items: center;height: 100%;}
.social-icon{display: flex; padding: 2%;}
.social-image{width: 80%;}
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
        <div class="selected-top-nav-item">
            PLANO
        </div>
        <div class= "vertical"></div>
        <a class="top-nav-item" href="/hall-of-fame">
            HALL OF FAME
        </a>
    </ul>
</nav>
<div class="padding-div"></div>
<div class="title">
    Plano Curricular
</div>
<div class="level-div">
    <span class="level-title">
        NIVEL 1- TUTORIAL - Aprende a teoria e as ferramentas básicas.
    </span>
    <div class="semester-container">
        <div class="semester-card">
            <div class="semester-title" onclick={ () => togglePanel(0)}>
                1º Semestre - Nível 1.1
            </div>
            {#if panels[0]}
            <div class="semester-description" transition:slide>
                Crítica e Análise de Videojogos - Sabes jogar, mas saberás mesmo analisar um jogo?<br>
                História dos Videojogos - Conhece a história do desenvolvimento de jogos, década a década.<br>
                Introdução à Imagem Digital - Aprende ferramentas básicas de criação de imagem (mesmo que não saibas desenhar!).<br>
                Design de Comunicação - Compreende noções de design, cor, equilíbrio e legibilidade (queres fazer jogos bonitos, certo?).<br>
                Fundamentos da Programação - Aprende as bases e fundamentos da programação.<br>
                Programação Criativa - Aplica a programação a situações concretas, de forma prática e criativa em Godot.<br>
            </div>
            {/if}
        </div>
        <div class="semester-card">
            <div class="semester-title" onclick={ () => togglePanel(1)}>
                2º Semestre - Nível 1.2
            </div>
            {#if panels[1]}
                <div class="semester-description" transition:slide>
                    Argumento e Narrativas Interativas - Aprende a criar histórias e narrativas não lineares<br>
                    Design de Interação - Para que alguém compreenda as tuas criações, tens que aprender as noções de interação e usabilidade.<br>
                    Animação Digital 2D - Dá vida aos teus personagens criando sets de animação para jogos, seja frame a frame ou por bones.<br>
                    Ilustração Digital I - Aprende a criar backgrounds, personagens e sprites usando diversas técnicas.<br>
                    Computação Gráfica - Compreende como funciona a computação gráfica e cria os teus primeiros modelos 3D.<br>
                    Linguagens de Programação I - Desenvolve conhecimentos sobre programação e C# usando o Unity 3D.<br>
                </div>
            {/if}
        </div>
    </div>
</div>
<div class="level-div">
    <span class="level-title">
        NIVEL 2- MAIN QUEST - Aventura-te e encontra o teu próprio caminho
    </span>
    <div class="semester-container">
        <div class="semester-card">
            <div class="semester-title" onclick={ () => togglePanel(2)}>
                1º Semestre - Nível 2.1
            </div>
            {#if panels[2]}
            <div class="semester-description" transition:slide>
                Desenvolvimento de Aplicações Multimédia - Descobre a enorme variedade e potencial das aplicações multimédia.<br>
                Ilustração Digital II - Desenvolve o teu próprio traço e explora a criação de estilos gráficos únicos.<br>
                Sistemas e Motores de Jogo - Compreende diferentes sistemas e motores criando uma série de micro jogos.<br>
                Modelação 3D - Pratica a Modelação e texturização de props, cenários e personagens.<br>
                Linguagens da Programação II - Aprofunda conhecimentos de Programação para jogos.<br>
                Projeto de Game Design I - Faz um pitch, trabalha em equipa e cria o teu primeiro jogo 2D.
            </div>
            {/if}
        </div>
        <div class="semester-card">
            <div class="semester-title" onclick={ () => togglePanel(3)}>
                2º Semestre - Nível 2.2
            </div>
            {#if panels[3]}
                <div class="semester-description" transition:slide>
                    Media Contemporâneos - Compreende os media nas suas variadas formas, de jogos a filmes e até memes!<br>
                    Atelier de Produção Multimédia e Web - Explora todas as potencialidades e criatividade da web.<br>
                    Introdução ao Design de Som - Aprende a criar ambientes sonoros envolventes.<br>
                    Animação Digital 3D - Dá vida aos teus modelos 3D e anima os teus heróis e NPCs.<br>
                    Linguagens de Programação III - Desenvolve sistemas complexos e aprende a usar o Unreal Engine.<br>
                    Projeto de Game Design II - Tomaste o gosto a criar jogos? O desafio agora ainda é maior, faz o teu jogo 3D.
                </div>
            {/if}
        </div>
    </div>
</div>
<div class="level-div">
    <span class="level-title">
        NIVEL 3- FINAL BOSS - Desenvolveste as tuas skills, está na hora de enfrentar o boss final.
    </span>
    <div class="semester-container">
        <div class="semester-card">
            <div class="semester-title" onclick={ () => togglePanel(4)}>
                1º Semestre - Nível 3.1
            </div>
            {#if panels[4]}
            <div class="semester-description" transition:slide>
                Atelier de Artes Digitais - Explora a visão por computador, sensores e formas alternativas de produzir arte digital.<br>
                Atelier de Realização de Videojogos e Aplicações Multimédia I - Dá início ao teu projeto de fim de curso.<br>
                Tecnologias do Audiovisual - Aprende a linguagem audiovisual para criares jogos ainda mais cinematográficos.
            </div>
            {/if}
        </div>
        <div class="semester-card">
            <div class="semester-title" onclick={ () => togglePanel(5)}>
                2º Semestre - Nível 3.2
            </div>
            {#if panels[5]}
                <div class="semester-description" transition:slide>
                    Atelier de Realização de Videojogos e Aplicações Multimédia II - Acaba o curso com o teu projeto mais ambicioso.<br>
                    Atelier de Marketing e Publicidade - Cria uma estratégia de Marketing e faz com que todos falem do teu projeto.<br>
                    Estágio e Integração Profissional - Estás pronto para enfrentar a vida profissional, mostra o que vales no teu estágio!
                </div>
            {/if}
        </div>
    </div>
</div>
<div class="footer-div">
    <div class="contact-div">
        <img src={phone} class="phone-ico">
        Tel: 222 073 230
        <img src={email} class="phone-ico">
        info.cup@ulusofona.pt <br>
        joao.alves.de.sousa@ulusofona.pt
    </div>
    <div class="socials">
        <a href="https://www.facebook.com/VAMULP/" class="social-icon">
            <img src={facebookIco} class="social-image">
        </a>
        <a href="https://www.facebook.com/VAMULP/" class="social-icon">
            <img src={instagramIco} class="social-image">
        </a>
        <a href="https://www.facebook.com/VAMULP/" class="social-icon">
            <img src={youtubeIco} class="social-image">
        </a>
    </div>
    <img scr={logoULP} class="logo-ulp">
</div>
