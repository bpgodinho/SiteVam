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

    import reference from '$lib/assets/Group 10.png'
    import prevIcon from '$lib/assets/Icons/prevIcon.png'
    import nextIcon from '$lib/assets/Icons/nextIcon.png'
    import {slide} from 'svelte/transition'
	import logo from '$lib/assets/Logos/logo_VAM_no_txt.png'
    import logo_white from '$lib/assets/Logos/logo_VAM_white.png'
    import phone from '$lib/assets/Icons/PhoneIcon.png'
    import email from '$lib/assets/Icons/EmailIcon.png'

    let index = $state(0)
	
	const next = () => {
        console.log(index)
		index = (index + 1) % carouselPhotos.length
	}

    const prev = () => {
        console.log(index)
		index = (index - 1 + carouselPhotos.length) % carouselPhotos.length
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

.about-carousel{width: 65%;margin-top: 65px; box-shadow: 0px 30px 60px 40px #2582137e;margin: 5%;border-radius: 45px;}
.carousel-container{display: flex; justify-content: center;align-items: center; padding: 8%;}
.carousel-control{width: 5%; cursor: pointer;}

.links-about{display: flex; justify-content: center; align-items: center; gap: 3%; padding-top: 5%; padding-bottom: 40%;}
.link-item{border-radius: 40px;background-color: #4a4a4a; font-size: 3vmin; color: white;
    font-family: "Outfit", sans-serif; width: 15%; text-align: center;padding: 3%; padding-top: 15%;padding-bottom: 15%;  box-shadow: 0px 10px 20px 10px #2582137e;}

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
    <img onclick={prev} src={prevIcon} class="carousel-control">
    <img src={carouselPhotos[index]} class="about-carousel">
    <img onclick={next} src={nextIcon} class="carousel-control">
</div>
<div class="links-about">
    <div class="link-item">
        PITCH VAM
    </div>
    <div class="link-item">
        DISCORD VAM
    </div>
    <div class="link-item">
        VAM GAME JAM
    </div>
    <div class="link-item">
        MOSTRA VAM
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
