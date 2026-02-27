# ua-engineering-website <!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>UA Engineering Private Limited</title>
<link rel="stylesheet" href="css/style.css">
</head>
<body>

<header>
<h1>UA Engineering Private Limited</h1>
<p>Professional Engineering Solutions for Your Projects</p>
</header>

<nav>
<a href="#home">Home</a>
<a href="#about">About</a>
<a href="#products">Products</a>
<a href="#contact">Contact</a>
</nav>

<div class="container" id="pdf-content">
<div class="watermark">UA ENGINEERING</div>

<section id="home">
<h2>Welcome to UA Engineering</h2>
<p>High-quality engineering solutions with professionalism and dedication.</p>
<a href="#contact" class="button">Get in Touch</a>
</section>

<section id="about">
<h2>About Us</h2>
<p>UA Engineering delivers industrial & construction engineering solutions with consulting, project management, and technical support.</p>
<img src="images/profile.jpg" alt="Company Profile" class="profile-img">
</section>

<section id="products">
<h2>Our Products</h2>
<div class="product-grid">
  <div class="product-card">
    <img src="images/switchgear.jpg" alt="Switchgear Panel">
    <h4>Switchgear Panel</h4>
    <p>High-quality panels for electrical distribution and safety.</p>
  </div>
  <div class="product-card">
    <img src="images/firealarm.jpg" alt="Fire Alarm System">
    <h4>Fire Alarm System</h4>
    <p>Reliable fire detection and alarm solutions.</p>
  </div>
  <div class="product-card">
    <img src="images/lightning.jpg" alt="Lightning Protection System">
    <h4>Lightning Protection System</h4>
    <p>Protect buildings and equipment from lightning strikes.</p>
  </div>
  <div class="product-card">
    <img src="images/earthing.jpg" alt="Earthing System">
    <h4>Earthing System</h4>
    <p>Durable and safe earthing solutions for electrical systems.</p>
  </div>
</div>
</section>

<section id="contact" class="contact-info">
<h2>Contact Us</h2>
<p><strong>Phone:</strong> (+92) 308-0728200</p>
<p><strong>Email:</strong> abubakarzulfiqar7869@gmail.com</p>
<p><strong>Address:</strong> Main Fatehpur Karor Road, near Faisal Bank, Fatehpur, District Layyah, Pakistan</p>
</section>

</div>

<button class="button" onclick="downloadPDF()">Download Print-Ready PDF</button>

<footer>
&copy; 2026 UA Engineering Private Limited. All Rights Reserved.
</footer>

<script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
<script src="js/main.js"></script>

</body>
</html>
* { margin:0; padding:0; box-sizing:border-box; }
body { font-family:'Roboto', sans-serif; background:#f4f7f9; color:#333; }
header { background:#0073e6; color:white; padding:60px 20px; text-align:center; position:relative; }
header h1 { font-size:3em; margin-bottom:10px; }
header p { font-size:1.2em; }
nav { display:flex; justify-content:center; background:#005bb5; flex-wrap:wrap; }
nav a { color:white; text-decoration:none; padding:15px 25px; font-weight:bold; transition:0.3s; }
nav a:hover { background:#004494; }
.container { width:90%; max-width:1100px; margin:40px auto; }
section h2 { font-size:2em; margin-bottom:20px; color:#0073e6; }
section p { font-size:1.1em; line-height:1.6; margin-bottom:10px; }
.button { display:inline-block; padding:12px 25px; background:#0073e6; color:white; border-radius:5px; text-decoration:none; font-weight:bold; }
.button:hover { background:#005bb5; cursor:pointer; }
.contact-info p { margin-bottom:10px; }
.profile-img { width:100%; max-width:300px; border-radius:10px; display:block; margin:15px auto; }
.product-grid { display:grid; grid-template-columns: repeat(auto-fit,minmax(200px,1fr)); gap:15px; }
.product-card { text-align:center; background:white; border-radius:10px; box-shadow:0 4px 8px rgba(0,0,0,0.1); padding:10px; }
.product-card img { width:100%; height:150px; object-fit:cover; border-radius:8px; }
footer { text-align:center; padding:20px; background:#005bb5; color:white; font-size:0.9em; margin-top:30px;}
function downloadPDF() {
  const { jsPDF } = window.jspdf;
  const element = document.getElementById('pdf-content');
  html2canvas(element, { scale:3 }).then(canvas => {
    const imgData = canvas.toDataURL('image/png');
    const pdf = new jsPDF('p','mm','a4');
    const pdfWidth = pdf.internal.pageSize.getWidth();
    const pdfHeight = (canvas.height * pdfWidth) / canvas.width;
    pdf.addImage(imgData, 'PNG', 0, 0, pdfWidth, pdfHeight);
    pdf.save('UA_Engineering_Profile.pdf');
  });
}
UA Engineering Website
======================

Folder Structure:
- index.html
- css/style.css
- js/main.js
- images/*

To deploy:
1. Zip the whole folder.
2. Upload to any web hosting (cPanel, Netlify, Vercel, GitHub Pages).
3. Open index.html in browser.

PDF Download:
- Click "Download Print‑Ready PDF" button to save profile PDF.
