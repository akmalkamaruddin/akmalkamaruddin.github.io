    title: Hi Tech Eng Solution Sdn Bhd | Engineering Excellence
    
<!DOCTYPE html>
<html lang="en">
<head>

 
    <style>
       * root {
            --primary: #004a99;
            --dark: #2d3436;
            --light: #f4f7f6;
            --white: #ffffff;
            --accent: #0984e3;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Segoe UI', sans-serif; }
        html { scroll-behavior: smooth; }
        body { background: var(--light); color: var(--dark); line-height: 1.6; }

        /* Navigation */
        nav {
            display: flex; justify-content: space-between; align-items: center;
            padding: 1rem 5%; background: var(--white);
            position: sticky; top: 0; z-index: 1000; box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        .logo { font-weight: bold; color: var(--primary); text-transform: uppercase; font-size: 1rem; }
        .nav-links { list-style: none; display: flex; }
        .nav-links li { margin-left: 20px; }
        .nav-links a { text-decoration: none; color: var(--dark); font-weight: 500; transition: 0.3s; }
        .nav-links a:hover { color: var(--primary); }

        .hamburger { display: none; cursor: pointer; flex-direction: column; gap: 5px; }
        .hamburger span { width: 25px; height: 3px; background: var(--primary); transition: 0.3s; }

        /* Hero */
        .hero {
            height: 60vh; display: flex; flex-direction: column;
            justify-content: center; align-items: center; text-align: center;
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), 
                        url('https://images.unsplash.com/photo-1581092160562-40aa08e78837?auto=format&fit=crop&w=1350&q=80');
            background-size: cover; color: white; padding: 20px;
        }

        /* Sections */
        section { padding: 80px 5%; }
        .section-title { text-align: center; margin-bottom: 40px; font-size: 2rem; color: var(--primary); }

        /* Services Grid */
        .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 20px; }
        .card { background: var(--white); padding: 30px; border-radius: 8px; text-align: center; transition: 0.3s; box-shadow: 0 4px 6px rgba(0,0,0,0.05); }
        .card:hover { transform: translateY(-10px); box-shadow: 0 10px 20px rgba(0,0,0,0.1); }

        /* Gallery Styles */
        .gallery-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; }
        .gallery-item { position: relative; overflow: hidden; border-radius: 8px; height: 200px; cursor: pointer; }
        .gallery-item img { width: 100%; height: 100%; object-fit: cover; transition: 0.5s ease; }
        .gallery-item:hover img { transform: scale(1.1); }
        .gallery-overlay {
            position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0, 74, 153, 0.7); display: flex; align-items: center; justify-content: center;
            color: white; opacity: 0; transition: 0.3s; text-align: center; padding: 10px;
        }
        .gallery-item:hover .gallery-overlay { opacity: 1; }

        /* Lightbox Modal */
        #lightbox {
            display: none; position: fixed; z-index: 3000; top: 0; left: 0;
            width: 100%; height: 100%; background: rgba(0,0,0,0.9);
            justify-content: center; align-items: center;
        }
        #lightbox img { max-width: 90%; max-height: 80%; border: 3px solid white; }
        .close-lightbox { position: absolute; top: 20px; right: 30px; color: white; font-size: 40px; cursor: pointer; }

        /* Back to Top Button */
        #backToTop {
            position: fixed; bottom: 30px; right: 30px;
            width: 50px; height: 50px; background: var(--primary);
            color: white; border: none; border-radius: 50%;
            cursor: pointer; display: none; font-size: 20px; z-index: 2000;
            box-shadow: 0 4px 10px rgba(0,0,0,0.3); transition: 0.3s;
        }

        /* Contact & Form */
        .contact-container { max-width: 600px; margin: 0 auto; background: var(--white); padding: 40px; border-radius: 10px; box-shadow: 0 5px 15px rgba(0,0,0,0.1); }
        input, textarea { width: 100%; padding: 12px; border: 1px solid #ddd; border-radius: 5px; font-size: 1rem; margin-bottom: 20px; }
        .btn-submit { width: 100%; background: var(--primary); color: white; border: none; padding: 15px; border-radius: 5px; font-weight: bold; cursor: pointer; }

        /* Map */
        .map-box { height: 400px; width: 100%; border-radius: 10px; overflow: hidden; margin-top: 20px; }
        iframe { width: 100%; height: 100%; border: 0; }

        footer { background: var(--dark); color: #bdc3c7; text-align: center; padding: 40px 20px; }

        @media (max-width: 768px) {
            .hamburger { display: flex; }
            .nav-links {
                display: none; flex-direction: column; position: absolute;
                top: 60px; right: 0; background: var(--white); width: 100%;
                text-align: center; box-shadow: 0 10px 10px rgba(0,0,0,0.1);
            }
            .nav-links.active { display: flex; }
            .nav-links li { margin: 15px 0; }
        }
    </style>
</head>
<body>

    <div id="lightbox">
        <span class="close-lightbox">&times;</span>
        <img id="lightbox-img" src="">
    </div>

    <button id="backToTop" title="Go to top">↑</button>

    <nav>
        <div class="logo">Hi Tech Eng Solution</div>
        <div class="hamburger" id="mobile-menu">
            <span></span><span></span><span></span>
        </div>
        <ul class="nav-links" id="nav-list">
            <li><a href="#home">Home</a></li>
            <li><a href="#services">Services</a></li>
            <li><a href="#gallery">Gallery</a></li>
            <li><a href="#location">Location</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <header id="home" class="hero">
        <h1>Hi Tech Eng Solution Sdn Bhd</h1>
        <p>Precision. Innovation. Excellence.</p>
    </header>

    <section id="services">
        <h2 class="section-title">Our Services</h2>
        <div class="grid">
            <div class="card"><h3>Solution Tools & Hardware</h3><p>Drafting and simulation for industry requirements.</p></div>
            <div class="card"><h3>System Integration</h3><p>Connecting hardware and software for seamless automation.</p></div>
            <div class="card"><h3>Consultancy</h3><p>Strategic engineering advice for various scale projects.</p></div>
        </div>
    </section>

    <section id="gallery" style="background: var(--white);">
        <h2 class="section-title">Project Gallery</h2>
        <div class="gallery-grid">
            <div class="gallery-item" onclick="openLightbox(this)">
               <!-- <img src="https://images.unsplash.com/photo-1537462715879-360eeb61a0ad?auto=format&fit=crop&w=1200" alt="Hardware">
                -->
                    <img src="https://lh3.googleusercontent.com/p/AF1QipN0Kq4g0XIvWSO3C4nPCQfXeKrmtIzpMCffkzY=s1360-w1360-h1020-rw" alt="Hardware">

                <div class="gallery-overlay">Hardware Solutions (Click to View)</div>
            </div>
            <div class="gallery-item" onclick="openLightbox(this)">
                <img src="https://images.unsplash.com/photo-1504917595217-d4dc5ebe6122?auto=format&fit=crop&w=1200" alt="System">
                <div class="gallery-overlay">System Integration (Click to View)</div>
            </div>
            <div class="gallery-item" onclick="openLightbox(this)">
                <img src="https://images.unsplash.com/photo-1518770660439-4636190af475?auto=format&fit=crop&w=1200" alt="Technical">
                <div class="gallery-overlay">Technical Parts (Click to View)</div>
            </div>
            <div class="gallery-item" onclick="openLightbox(this)">
                <img src="https://lh3.googleusercontent.com/gps-cs-s/AHVAwerQInPY5VgQmEfbT53uDAgB3Jy1Xzjgln_8Tp9G4nQ8QEPLej838eOh0zBhNDacwBQXEperXLgqxJ_VxTCPM47hWT-nJHn4Mazd-XnDvyiuX59JF-AC6N9vRgLqcFKIxbDyZJIl=s1360-w1360-h1020-rw" alt="Industry">
                <div class="gallery-overlay">Industry Projects (Click to View)</div>
            </div>
        </div>
    </section>

    <section id="location">
        <h2 class="section-title">Visit Us</h2>
        <div class="map-box">
          <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d7968.802419444002!2d101.65532184416209!3d2.9860293527880444!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x31cdb452c629b0a7%3A0xa4850a45c0e6b8dc!2sHi%20Tech%20Eng%20Solution%20Sdn%20Bhd!5e0!3m2!1sen!2smy!4v1772218489829!5m2!1sen!2smy" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
        </div>
    </section>

    <section id="contact" style="background: var(--white);">
        <h2 class="section-title">Contact Us</h2>
        <div class="contact-container">
            <form id="contactForm">
                <input type="text" id="name" placeholder="Full Name" required>
                <input type="text" id="subject" placeholder="Subject" required>
                <textarea id="message" placeholder="Message" required></textarea>
                <button type="submit" class="btn-submit">Send Message</button>
            </form>
        </div>
    </section>

    <footer>
        <p>© 2026 Hi Tech Eng Solution Sdn Bhd. All Rights Reserved.</p>
        <p>Email: admin@htesb.com</p>
 
 
<!-- Start of Global Code -->
<script type="text/javascript" src="https://counter.websiteout.com/js/17/5/499/0"></script>

<script>
        // Lightbox Logic
        const lightbox = document.getElementById('lightbox');
        const lightboxImg = document.getElementById('lightbox-img');

        function openLightbox(element) {
            const imgSrc = element.querySelector('img').src;
            lightboxImg.src = imgSrc;
            lightbox.style.display = 'flex';
        }

        lightbox.onclick = function(e) {
            if (e.target !== lightboxImg) {
                lightbox.style.display = 'none';
            }
        };

        // Back to Top Logic
        const topBtn = document.getElementById("backToTop");
        window.onscroll = function() {
            if (document.body.scrollTop > 300 || document.documentElement.scrollTop > 300) {
                topBtn.style.display = "block";
            } else {
                topBtn.style.display = "none";
            }
        };
        topBtn.onclick = function() {
            window.scrollTo({top: 0, behavior: 'smooth'});
        };

        // Mobile Menu Logic
        const menu = document.getElementById('mobile-menu');
        const navList = document.getElementById('nav-list');
        menu.onclick = () => navList.classList.toggle('active');

        // Form Logic
        document.getElementById('contactForm').onsubmit = function(e) {
            e.preventDefault();
            const mailtoLink = `mailto:admin@htesb.com?subject=${encodeURIComponent(document.getElementById('subject').value)}&body=${encodeURIComponent(document.getElementById('message').value)}`;
            window.location.href = mailtoLink;
        };
</script>
</footer>
</body>
</html>

<!--
<!DOCTYPE html>
<html lang="eng">
<meta name="viewport" content="width=device-width initial-scale=1 minimum-scale=1.0 maximum-scale=1.0"/>

<head>
<title>Copyright by Hi Tech Eng Solution Sdn Bhd</title>
</head>

<header>
<h3>

<img src="https://readme-typing-svg.herokuapp.com/?font=Righteous&size=30&center=true&vCenter=true&width=400&height=45&duration=4000&lines=©️ Hi Tech Eng Solution Sdn Bhd ;+admin@htesb.com;"/>

</h3>

</header>

<body style="width: 100%; height: 100%;">
<iframe width="100%" height="720px" frameborder="0" src="https://htesb.speedtestcustom.com">
</iframe>

</body>

</html>-->
