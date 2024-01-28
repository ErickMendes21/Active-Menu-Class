<!-- Html: -->

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="styles.css">
    <title>Document</title>
</head>
<body>
    <header>
        <a href="#" class="logo">Activelink.</a>  
        <nav>
            <a href="#home" class="active">Home</a>
            <a href="#about">About</a>
            <a href="#servicee">Service</a>
            <a href="#portifolio">Portifolio</a>
            <a href="#contact">Contact</a>
        </nav>
    </header>

    <section id="home">Home</section>
    <section id="about">About</section>
    <section id="servicee">Services</section>
    <section id="portifolio">Portifolio</section>
    <section id="contact">Contact</section>

    <script src="script.js"></script>
</body>
</html>
<!-- Css: -->
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Poppins';
}

header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    padding: 20px 120px;
    background: #11141a;
    display: flex;
    justify-content: space-between;
    align-items: center;
    z-index: 100;
}

.logo {
    font-size: 25px;
    color: #fff;
    text-decoration: none;
    font-weight: 600;
}

nav a {
    font-size: 18px;
    color:#fff;
    text-decoration: none;
    font-weight: 500;
    margin-left: 35px;
    transition: .3s;
}

nav a:hover, 
nav a.active{
    color: #0ef;
}

section {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: #1f242d;
    font-size: 100px;
    color: #fff;
    font-weight: 700;
}

section:nth-child(odd) {
    background-color: #323946;
}

<!-- JavaScript: -->
let sections = document.querySelectorAll('section');
let navLinks = document.querySelectorAll('header nav a');

window.onscroll = () => {
    sections.forEach(sec => {
        let top = window.scrollY;
        let offset = sec.offsetTop;
        let height = sec.offsetHeight;
        let id = sec.getAttribute('id');

        if(top >= offset && top < offset + height) {
          navLinks.forEach(links => {
            links.classList.remove('active');
            document.querySelector ('header nav a[href*='+ id +']').classList.add('active');
          })  
        };
    })
}
