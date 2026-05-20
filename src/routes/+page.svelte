<script>
	import logo from '$lib/assets/Logos/logo_VAM_no_txt.png'
    import logo_white from '$lib/assets/Logos/logo_VAM_white.png'
    import main_vid from '$lib/assets/SHOWREEL_Vam25.mp4'
    import reference from '$lib/assets/Slide 16_9 - 1.png'
    import shapes1 from '$lib/assets/Shapes/ShapeFlair1.png'
    import shapes2 from '$lib/assets/Shapes/ShapeFlair2.png'
    import shapes3 from '$lib/assets/Shapes/ShapeFlair3.png'
    import shapes4 from '$lib/assets/Shapes/ShapeFlair4.png'
    import phone from '$lib/assets/Icons/PhoneIcon.png'
    import email from '$lib/assets/Icons/EmailIcon.png'
</script>

<style>
:global(body) {margin: 0px; padding: 0px; overflow-x: hidden;}

.reference{position: absolute; width: 100%;z-index: -99;}
.top-nav{position: fixed; display:flex; height: 65px; width:100%; background-color:#4d4c4c;z-index: 2;}
.vam-logo{max-height: 100%; height:auto; padding: 0.75%; padding-left: 3%;}
.nav-list{position: absolute; display:flex; justify-content: center; align-items: center; width: 100%; height: 100%; margin: 0%; padding: 0%;}
.top-nav-item{font-family: "Outfit", sans-serif;font-size: x-large; font-weight: 200; color: white;padding-left: 0%;text-decoration:none;}
.selected-top-nav-item{font-family: "Outfit", sans-serif;font-size: x-large; font-weight: 200; color: #23d400;padding-left: 0%;}
.vertical{margin: 10px;border-left: 2px solid white;height: 20px; }

.video-container{position: relative;background-color: #292929;}
.main_vid{width: 100%;margin-top: 65px; box-shadow: 0px 0px 60px 60px #2582137e; z-index: 2;}
.block-controls{position: absolute; top: 65px; left: 0; width: 100%; height: 100%; z-index: 1;}
.shapes1-vid{position: absolute; width: 30%;left: 0%;bottom: 0%;}
.shapes2-vid{position: absolute; width: 30%;right: 0%;top: 7%;}

.about-div{position:relative; display:flex; justify-content: center; background-color:#292929;align-items: center;padding-left: 8%;padding-right: 4%; padding-top: 243px;padding-bottom: 750px; z-index: -1;}
.about-title{border-radius: 40px;background-color: #1f4618; font-size: 18vmin; color: white;font-family: "Outfit", sans-serif; width: 50%; text-align: center; font-weight: bold;}
.about-description{border-radius: 65px;background-color: #4a4a4a; font-size: 3vmin; color: white;font-family: "Outfit", sans-serif; width: 55%; margin-left: 2.5%; padding: 2%;line-height: 43px;}
.shapes1-about{position: absolute; width: 52%;left: -5%;top: 10%;z-index: -1;}
.shapes2-about{position: absolute; width: 45%;right: -12%;bottom: 0%;}

.footer-div{background-color:#2d7328; height: 70px; display: flex; bottom: 0px;}
.contact-logo{max-height: 100%; height:auto; padding: 0.75%; padding-left: 3%;}
.contact-div{align-content: center; font-family: "Outfit", sans-serif;font-size: 2.5vmin; margin-left: 2%;color: white;height: 70px;display: flex;align-items: center;width: 45%;}
.phone-ico{max-height: 40%;margin-left: 5%; margin-right: 1%;}
</style>

<nav class="top-nav">
    <img class="vam-logo" alt="Vam Logo" src={logo}>
    <ul class="nav-list">
        <div class="selected-top-nav-item">
            HOME
        </div>
        <div class= "vertical"></div>
        <a class="top-nav-item" href="/about">
            SOBRE
        </a>
        <div class= "vertical"></div>
        <div class="top-nav-item">
            JOGOS
        </div>
        <div class= "vertical"></div>
        <div class="top-nav-item">
            ARTIGOS
        </div>
    </ul>
</nav>
<div class="video-container">
    <div class="block-controls"></div>
    <video autoplay muted loop src={main_vid} class="main_vid"></video>
    <img src={shapes1} class="shapes1-vid">
    <img src={shapes2} class="shapes2-vid">
</div>
<div class="about-div">
    <div class="about-title">
        SOBRE
    </div>
    <div class="about-description">
        VAM é uma Licenciatura com uma componente prática intensa que te prepara para o mercado de trabalho.<br>
        Não sabes se gostarias de seguir o campo da programação, da arte, sonoplastia ou game design?<br>
        Estás no local certo, pois terás a oportunidade de aprender e experimentar todas essas áreas tendo uma visão abrangente dos principais processos e trabalhos no campo do desenvolvimento de Videojogos e Aplicações Multimédia.<br>
        Os projetos de grupo que desenvolvemos permitirão que te especializes nas áreas que demonstres mais capacidades, desta forma, a formação de cada estudante é personalizada e em cada turma são desenvolvidos perfis distintos.
    </div>
    <img src={shapes3} class="shapes1-about">
    <img src={shapes4} class="shapes2-about">
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
