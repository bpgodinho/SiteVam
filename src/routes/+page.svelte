<script>
	import logo_no_txt from '$lib/assets/Logos/logo_VAM_no_txt.png'
    import logo_white from '$lib/assets/Logos/logo_VAM_white.png'
    import main_vid from '$lib/assets/SHOWREEL_Vam25.mp4'
    import reference from '$lib/assets/Slide 16_9 - 1.png'
    import shapes1 from '$lib/assets/Shapes/ShapeFlair1.png'
    import shapes2 from '$lib/assets/Shapes/ShapeFlair2.png'
    import shapes3 from '$lib/assets/Shapes/ShapeFlair3.png'
    import shapes4 from '$lib/assets/Shapes/ShapeFlair4.png'
    import logo from '$lib/assets/Logos/logo_VAM.png'
    import phone from '$lib/assets/Icons/PhoneIcon.png'
    import email from '$lib/assets/Icons/EmailIcon.png'
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

.video-container{position: relative;background-color: #292929;}
.main_vid{width: 100%;margin-top: 65px; box-shadow: 0px 0px 60px 60px #2582137e; z-index: 2;}
.block-controls{position: absolute; top: 65px; left: 0; width: 100%; height: 100%; z-index: 1;}
.shapes1-vid{position: absolute; width: 30%;left: 0%;bottom: 0%;}
.shapes2-vid{position: absolute; width: 30%;right: 0%;top: 7%;}

.about-div{position:relative; display:flex; justify-content: center; background-color:#292929;align-items: center;padding-left: 5%;
    padding-right: 1%; padding-top: 243px;padding-bottom: 750px;}
.about-logo{width: 35%; padding-right: 5%;}
.about-description{position:relative;border-radius: 65px;background-color: #1a1a1a; font-size: 2.4vmin; color: white;
    font-family: "Outfit", sans-serif; width: 40%; margin-left: 5%; padding: 5%; padding-top:4%; box-shadow: 0px 0px 20px 20px #2582135c; -webkit-text-stroke: 0.03vmin #23d400;}
.sign-up-button{position:absolute;left: 50%;bottom: 0%; transform: translate(-50%,75%);background-color: #040404; padding: 6%;
    width:50%;-webkit-text-stroke: 0vmin #23d400; font-size: 5.5vmin; text-align: center; border-radius: 45px;
    border: 0.1vmin solid #23d400; box-shadow: 0px 10px 20px 20px #2582135c; cursor: pointer; text-decoration: none;color: white;z-index: 2;}
.shapes1-about{position: absolute; width: 52%;left: -5%;top: 10%;z-index: -1;}
.shapes2-about{position: absolute; width: 45%;right: -12%;bottom: 0%;}

.footer-div{background-color:#2d7328; height: 70px; display: flex; bottom: 0px;}
.contact-logo{max-height: 100%; height:auto; padding: 0.75%; padding-left: 3%;}
.contact-div{align-content: center; font-family: "Outfit", sans-serif;font-size: 2vmin; margin-left: 2%;color: white;height: 70px;display: flex;align-items: center;width: 45%;}
.phone-ico{max-height: 40%;margin-left: 5%; margin-right: 1%;}
</style>

<nav class="top-nav">
    <img class="vam-logo" alt="Vam Logo" src={logo_no_txt}>
    <ul class="nav-list">
        <div class="selected-top-nav-item">
            HOME
        </div>
        <div class= "vertical"></div>
        <a class="top-nav-item" href="/about">
            SOBRE
        </a>
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
<div class="video-container">
    <div class="block-controls"></div>
    <video autoplay muted loop src={main_vid} class="main_vid"></video>
    <img src={shapes1} class="shapes1-vid">
    <img src={shapes2} class="shapes2-vid">
</div>
<div class="about-div">
    <img src={logo} class="about-logo">
    <div class="about-description">
        A Licenciatura em Videojogos e Aplicações Multimédia (VAM) da Universidade Lusófona Porto está organizada em 3 níveis correspondentes aos 3 anos do curso.<br><br>
        Vencemos o Prémio Fazer + “Melhor Prática Pedagógica Inovadora” em reconhecimento da nossa estratégia pedagógica que usa a metodologia de Project Based Learning (PBL).<br><br>
        Isso significa que aprenderás enquanto crias os teus projetos e desenvolves o teu portfólio, seguindo o teu próprio caminho num processo de trabalho aliciante e motivador.<br><br>
        Jogamos, analisamos e sonhamos com os mundos virtuais que juntos iremos criar.
        <a class="sign-up-button" href="https://www.ulusofona.pt/porto/licenciaturas/videojogos-e-aplicacoes-multimedia">
            Candidata-te!
        </a>
    </div>
    <img src={shapes3} class="shapes1-about">
    <img src={shapes4} class="shapes2-about">
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
