<nav>
    <a href="/">home</a>
    <a href="/detect_emotions">detect-emotions</a>
</nav>

<slot></slot>

<footer>
    <p>
        Created with <i class="fas fa-heart heart"></i> By <b>Suayeb Ahmed</b>
        <a href="https://github.com/suayebahmed"><i class="fab fa-github"></i></a>
        <a href="https://www.linkedin.com/in/suayeb-ahmed/"><i class="fab fa-linkedin"></i></a>
    </p>
</footer>

<style>
    @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;800&family=Noto+Serif:wght@400;500;700&family=Poppins&family=Space+Mono:ital,wght@0,400;0,700;1,700&display=swap');

    :global(body) {
        margin: 0 auto;
        padding: 0;
        width: 60%;
        font-family: 'JetBrains Mono', monospace;    
    }

    nav {
        display: inline-block;
        padding: 30px 0;
    }

    nav a {
        margin-right: 20px;
        /* text-decoration: none; */
        text-underline-offset: 5px;
        text-decoration-color: yellowgreen;
        text-decoration-thickness: 3px;
        text-decoration-style: wavy;
        color: #000;
    }

    nav a:hover {
        color: yellowgreen;
    }

    footer {
        /* Put the footer at the bottom of the website */
        position: fixed;
        bottom: 50px;
        color: #000;
    }

    footer a {
        color: rgb(0, 186, 249);
    }

    .heart {
        color: red;
    }

    footer a:hover {
        color: yellowgreen;
    }

</style>