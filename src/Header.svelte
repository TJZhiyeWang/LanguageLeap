<script>
    export let title = "LINGUEE";
</script>

<header>
    <div class="logo-container">
        <img class="logo" src="images/logo.jpg" alt="Your Logo" />
    </div>
    <div class="title">
        <h1>{title}</h1>
    </div>
</header>

<style>
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        background-color: #f0f0f0;
        box-shadow: 0 rgba(0, 0, 0, 0.1);
    }

    .title {
        margin-right: 5%;
        font-size:larger;
    }
    
    .logo-container {
        display: flex;
        align-items: center;
    }

    .logo {
        max-width: 100px;
        max-height: 100px;
    }
</style>
