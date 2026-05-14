<script>
	import logo from '$lib/assets/Logos/logo_VAM_no_txt.png'
    import reference from '$lib/assets/Reference.png'
</script>

<style>
:global(body) {margin: 0; padding: 0; }
.reference{position: absolute; width: 100%;}
.top-nav{position: fixed; display:flex; height: 10%; width:100%; background-color:rgba(128, 128, 128, 0.27);}
.vam-logo{max-height: 100%; height:auto; padding: 0.75%; padding-left: 3%;}
.nav-list{display:flex; justify-content: center; align-items: center; width: 100%; height: 100%; margin: 0%; padding: 0%;}
.top-nav-item{font-family: Outfit;}
</style>

<img class="reference" alt="reference" src={reference}>
<nav class="top-nav">
    <img class="vam-logo" alt="Vam Logo" src={logo}>
    <ul class="nav-list">
        <div class="top-nav-item">
            teste
        </div>
    </ul>
</nav>