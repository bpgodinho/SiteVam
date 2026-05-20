<script>
    import {fade} from 'svelte/transition';

    import reference from '$lib/assets/Group 10.png'
	import logo from '$lib/assets/Logos/logo_VAM_no_txt.png'
    import logo_white from '$lib/assets/Logos/logo_VAM_white.png'
    import phone from '$lib/assets/Icons/PhoneIcon.png'
    import email from '$lib/assets/Icons/EmailIcon.png'

    import foxThumbnail from '$lib/assets/Games/FoxGame.png'

    const gameImages = [
        '/GamePhotos/FoxGame.png',
        '/GamePhotos/TypeAdventure.png',
    ];

    let popupOpen = $state(false);
    let popupImageIdx = $state(0);
    let makeIdx = 0;

    const preIdx = (idx) => {
        makeIdx = idx;
    }

    const showPopup = () => {
        popupImageIdx = makeIdx;
        popupOpen = true;
    }



</script>

<style>
:global(body) {margin: 0px; padding: 0px; overflow-x: hidden;background-color: #292929;}

.reference{position: absolute; width: 100%;z-index: -99;}
.popup-ref{position: fixed; width: 90%;z-index: 99; opacity: 0.5;top: 10%; left: 5%;}
.top-nav{position: fixed; display:flex; height: 65px; width:100%; background-color:#4d4c4c;z-index: 2;}
.vam-logo{max-height: 100%; height:auto; padding: 0.75%; padding-left: 3%;}
.nav-list{position: absolute; display:flex; justify-content: center; align-items: center; width: 100%; height: 100%; margin: 0%; padding: 0%;}
.top-nav-item{font-family: "Outfit", sans-serif;font-size: x-large; font-weight: 200; color: white;padding-left: 0%;text-decoration:none;}
.selected-top-nav-item{font-family: "Outfit", sans-serif;font-size: x-large; font-weight: 200; color: #23d400;padding-left: 0%;}
.vertical{margin: 10px;border-left: 2px solid white;height: 20px; }

.title{display: flex; font-family: "Outfit", sans-serif;font-size: 10vmin; font-weight: bold; color: white;text-align: center;justify-self: center;padding-top: 100px;padding-bottom: 1%;}

.game-grid{display: grid; grid-template-columns: repeat(4, 22%); gap: 3%; padding: 2%; justify-content: center; row-gap: 7%; padding-bottom: 10%;}
.game-card{position: relative; background-color: #4a4a4a; border-radius: 3vw; box-shadow: 0px 10px 20px 10px #2582137e; display: flex; justify-content: center; align-items: center;}
.game-image{width: 100%; border-radius: 3vw;}
.game-image:hover{transform: scale(1.1); transition: transform 0.3s ease-in-out;}

.game-popup{position: fixed; display: flex; left: 8%; top: 15%; max-width: 80%;height: 65%; align-items: center; background-color: #4a4a4a; border-radius: 3vw;
    box-shadow: 0px 10px 30px 20px #2582137e; padding: 2%; font-family: 'Outfit', sans-serif;}
.popup-image{ border-radius: 3vw; margin-right: 5%;height: 90%;}
.close-icon{position: absolute; width: 5%; top: 5%; right: 2%; cursor: pointer;}
.popup-description{width: 50%; color: white; display: flex; flex-direction: column; gap: 2%;justify-content: center;align-items: center; height: 100%;}

.footer-div{background-color:#2d7328; height: 70px; display: flex; bottom: 0px;}
.contact-logo{max-height: 100%; height:auto; padding: 0.75%; padding-left: 3%;}
.contact-div{align-content: center; font-family: "Outfit", sans-serif;font-size: 2.5vmin;
    margin-left: 2%;color: white;height: 70px;display: flex;align-items: center;width: 45%;}
.phone-ico{max-height: 40%;margin-left: 5%; margin-right: 1%;}
</style>

<!--<img src={reference} class="reference">-->
<!--<img src={reference} class="popup-ref">-->
<nav class="top-nav">
    <img class="vam-logo" alt="Vam Logo" src={logo}>
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
            JOGOS
        </div>
        <div class= "vertical"></div>
        <a class="top-nav-item" href="/articles">
            ARTIGOS
        </a>
    </ul>
</nav>
<span class="title">
    JOGOS
</span>
<div class="game-grid">
    <div class="game-card">
        <img src={foxThumbnail} class="game-image" onclick={ () => {preIdx(1); showPopup();}}>
    </div>
    <div class="game-card">
        <img src={foxThumbnail} class="game-image" onclick={ () => {preIdx(1); showPopup();}}>
    </div>
    <div class="game-card">
        <img src={foxThumbnail} class="game-image" onclick={ () => {preIdx(1); showPopup();}}>
    </div>
    <div class="game-card">
        <img src={foxThumbnail} class="game-image" onclick={ () => {preIdx(1); showPopup();}}>
    </div>
    <div class="game-card">
        <img src={foxThumbnail} class="game-image" onclick={ () => {preIdx(1); showPopup();}}>
    </div>
    <div class="game-card">
        <img src={foxThumbnail} class="game-image" onclick={ () => {preIdx(1); showPopup();}}>
    </div>
    <div class="game-card">
        <img src={foxThumbnail} class="game-image" onclick={ () => {preIdx(1); showPopup();}}>
    </div>
    <div class="game-card">
        <img src={foxThumbnail} class="game-image" onclick={ () => {preIdx(1); showPopup();}}>
    </div>
</div>
{#if popupOpen}
    <div class="game-popup" transition:fade={{ duration: 300 }}>
        <img src={gameImages[popupImageIdx]} class="popup-image">
        <div class="popup-description">
            <span style="font-size: 10vmin;">Fox Game</span>
            <span style="font-size: 6vmin;">Genero</span><br>
            <span style="font-size: 3vmin;">
                DESCRICAO DO JOGO BEM DESCRITIVA PARA QUE O JOGO SEJA DESCRITO E AS PESSOAS FIQUEM COM VONTADE DE JOGAR O JOGO E TALVEZ INCLUA ALGUMAS IMAGENS DO JOGO PARA FICAR MAIS INTERESSANTE
            </span>
        </div>
        <img src={email} alt="close-icon" class="close-icon" onclick={() => popupOpen = !popupOpen}>
    </div>
{/if}
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
