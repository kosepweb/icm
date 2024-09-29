<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Landing Page - Company Profile</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
    <style>
        /* Global Styles */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Roboto', sans-serif; /* Menggunakan font Roboto */
            background: #f7f7f7;
            color: #333;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            transition: background-color 0.5s ease;
            line-height: 1.6; /* Menambah jarak antar baris untuk kenyamanan baca */
        }

        /* Container Styles */
        .container, .company-profile {
            width: 100%;
            max-width: 1200px;
            margin: auto;
            padding: 40px 20px;
            text-align: center;
            transition: transform 0.5s ease, opacity 0.5s ease;
        }

        /* Landing Page Styles */
        .container {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            color: #fff;
            background-image: url('icm.jpg'); /* Ganti dengan gambar latar */
            background-size: cover;
            background-position: center;
            position: relative;
            overflow: hidden;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.5); /* Menambah bayangan */
        }

        .container::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.5); /* Overlay gelap */
            z-index: 1;
        }

        .container h1 {
            font-size: 48px;
            margin-bottom: 20px;
            z-index: 2;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7);
        }

        .container p {
            font-size: 24px;
            margin-bottom: 40px;
            z-index: 2;
        }

        .btn {
            padding: 15px 30px;
            background-color: #fff;
            color: #2575fc;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            font-size: 18px;
            z-index: 2;
            transition: background-color 0.3s, transform 0.3s, box-shadow 0.3s;
        }

        .btn:hover {
            background-color: #e0e0e0;
            transform: scale(1.05);
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.4);
        }

        /* Company Profile Styles */
        .company-profile {
            display: none;
            padding-top: 80px;
        }

        .company-profile h2 {
            font-size: 36px;
            margin-bottom: 20px;
            color: #2575fc;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .section {
            background-color: #fff;
            padding: 40px 20px;
            margin-bottom: 40px;
            border-radius: 10px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            position: relative; /* Untuk efek border */
            overflow: hidden; /* Menyembunyikan overflow */
        }

        .section:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 25px rgba(0, 0, 0, 0.2);
        }

        .section h3 {
            font-size: 28px;
            margin-bottom: 20px;
            color: #2575fc;
            text-transform: uppercase;
            position: relative;
        }

        .section h3::after {
            content: '';
            width: 50px;
            height: 3px;
            background-color: #2575fc;
            position: absolute;
            bottom: -10px;
            left: 0;
        }

        .section p, .section ul {
            font-size: 18px;
            color: #555;
            margin-bottom: 15px; /* Menambah jarak antar paragraf */
        }

        .section ul {
            list-style: disc;
            padding-left: 20px;
        }

        /* Layanan dan Keunggulan Styles */
        .services, .advantages {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            margin-top: 20px;
        }

        .service, .advantage-item {
            flex: 1;
            margin: 10px;
            padding: 20px;
            border: 1px solid #e0e0e0;
            border-radius: 10px;
            text-align: center;
            transition: transform 0.3s, box-shadow 0.3s;
            font-weight: 500; /* Menambah ketebalan font */
        }

        .service:hover, .advantage-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
        }

        .service i, .advantage-item i {
            font-size: 36px;
            color: #2575fc;
            margin-bottom: 10px;
        }

        /* Portfolio Styles */
        .portfolio {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            margin-top: 20px;
        }

        .portfolio-item {
            width: calc(33% - 20px);
            margin: 10px;
            overflow: hidden;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
        }

        .portfolio-item img {
            width: 100%;
            border-radius: 10px;
            transition: transform 0.3s ease;
        }

        .portfolio-item:hover img {
            transform: scale(1.05); /* Zoom in saat hover */
        }

        /* Team Styles */
        .team {
            display: flex;
            justify-content: space-around;
            margin-top: 20px;
            flex-wrap: wrap; /* Membuat tampilan responsif */
        }

        .team-member {
            text-align: center;
            width: 20%;
            transition: transform 0.3s ease;
            margin-bottom: 20px; /* Menambah jarak antar anggota tim */
        }

        .team-member:hover {
            transform: translateY(-5px);
        }

        .team-member img {
            width: 80%; /* Mengatur lebar gambar */
            border-radius: 50%;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        }

        /* Contact Form Styles */
        .contact-form {
            display: flex;
            flex-direction: column;
            margin-top: 20px;
        }

        .contact-form input, .contact-form textarea {
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            transition: border-color 0.3s;
            font-size: 16px; /* Menyesuaikan ukuran font */
        }

        .contact-form input:focus, .contact-form textarea:focus {
            border-color: #2575fc;
            outline: none;
        }

        .contact-form button {
            padding: 10px;
            background-color: #2575fc;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
            font-size: 16px; /* Menyesuaikan ukuran font */
        }

        .contact-form button:hover {
            background-color: #0056b3;
        }

        /* Social Media Icons */
        .social-icons {
            margin-top: 20px;
            font-size: 24px;
            color: #2575fc;
        }

        .social-icons a {
            margin: 0 15px;
            transition: color 0.3s;
        }

        .social-icons a:hover {
            color: #0056b3;
        }

        /* Footer Styles */
        footer {
            text-align: center;
            padding: 20px;
            background: #fff;
            width: 100%;
            box-shadow: 0 -1px 5px rgba(0, 0, 0, 0.1);
            margin-top: 40px;
            font-size: 14px; /* Menyesuaikan ukuran font footer */
        }

        /* Media Queries */
        @media (max-width: 768px) {
            .service, .advantage-item {
                flex: 1 0 45%; /* Menyesuaikan ukuran di layar kecil */
            }

            .portfolio-item {
                width: calc(50% - 20px); /* Menyesuaikan ukuran gambar di layar kecil */
            }

            .team-member {
                width: 45%; /* Menyesuaikan ukuran anggota tim di layar kecil */
            }

            .container h1 {
                font-size: 36px;
            }

            .container p {
                font-size: 20px;
            }
        }

        @media (max-width: 480px) {
            .service, .advantage-item {
                flex: 1 0 100%; /* Menyesuaikan ukuran di layar kecil */
            }

            .portfolio-item {
                width: 100%; /* Menyesuaikan ukuran gambar di layar kecil */
            }

            .team-member {
                width: 100%; /* Menyesuaikan ukuran anggota tim di layar kecil */
            }

            .container h1 {
                font-size: 28px; /* Mengurangi ukuran font di perangkat kecil */
            }

            .container p {
                font-size: 18px; /* Mengurangi ukuran font di perangkat kecil */
            }

            .btn {
                font-size: 16px; /* Menyesuaikan ukuran font tombol di perangkat kecil */
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Selamat Datang di Inspirasi Cemerlang Mekongga</h1>
        <p>Event Organizer Profesional untuk Acara Anda</p>
        <button id="nextButton" class="btn">Lihat Profil Perusahaan</button>
    </div>

    <div class="company-profile" id="companyProfile">
        <h2>Profil Perusahaan</h2>

        <!-- Tentang Kami Section -->
        <div class="section">
            <h3>Tentang Kami</h3>
            <p>Kami, Inspirasi Cemerlang Mekongga, adalah tim profesional yang berdedikasi untuk membuat setiap acara menjadi momen yang tak terlupakan. Dengan pengalaman lebih dari 10 tahun di industri event, kami memahami pentingnya detail dan kualitas dalam setiap acara yang kami kelola.</p>
            <p>Kami mengutamakan kepuasan klien dan berkomitmen untuk memberikan layanan terbaik dengan memanfaatkan teknologi terkini. Apakah itu pernikahan, konferensi, atau acara perusahaan, kami siap membantu Anda merencanakan dan melaksanakan acara impian Anda.</p>
        </div>

        <div class="section">
            <h3>Visi dan Misi</h3>
            <p>Visi kami adalah memberikan layanan terbaik untuk setiap acara yang kami tangani, dengan misi:</p>
            <ul>
                <li>Menghadirkan pengalaman yang tidak terlupakan bagi klien.</li>
                <li>Memanfaatkan teknologi untuk meningkatkan kualitas layanan.</li>
                <li>Berkomitmen terhadap keberlanjutan dan tanggung jawab sosial.</li>
            </ul>
        </div>

        <div class="section">
            <h3>Layanan Kami</h3>
            <div class="services">
                <div class="service">
                    <i class="fas fa-calendar-alt fa-3x"></i>
                    <h4>Perencanaan Acara</h4>
                    <p>Kami membantu Anda merencanakan acara yang sempurna dari awal hingga akhir.</p>
                </div>
                <div class="service">
                    <i class="fas fa-microphone fa-3x"></i>
                    <h4>Penyewaan Peralatan</h4>
                    <p>Penyewaan peralatan audio dan visual yang berkualitas tinggi untuk acara Anda.</p>
                </div>
                <div class="service">
                    <i class="fas fa-users fa-3x"></i>
                    <h4>Manajemen Acara</h4>
                    <p>Tim profesional kami siap membantu mengelola acara Anda dengan lancar.</p>
                </div>
            </div>
        </div>

        <div class="section advantages">
            <h3>Keunggulan Kami</h3>
            <div class="advantages">
                <div class="advantage-item">
                    <i class="fas fa-check-circle"></i>
                    <p>Pengalaman lebih dari 10 tahun dalam industri event.</p>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-thumbs-up"></i>
                    <p>Ulasan positif dari lebih dari 500 klien.</p>
                </div>
                <div class="advantage-item">
                    <i class="fas fa-star"></i>
                    <p>Tim profesional yang berkomitmen terhadap kesempurnaan.</p>
                </div>
            </div>
        </div>

        <div class="section">
            <h3>Portofolio</h3>
            <div class="portfolio">
                <div class="portfolio-item">
                    <img src="portofolio1.jpg" alt="Portofolio 1">
                </div>
                <div class="portfolio-item">
                    <img src="portofolio2.jpg" alt="Portofolio 2">
                </div>
                <div class="portfolio-item">
                    <img src="portofolio3.jpg" alt="Portofolio 3">
                </div>
            </div>
        </div>

        <div class="section">
            <h3>Klien Kami</h3>
            <img src="our_clients.jpg" alt="Our Clients" style="width: 100%; border-radius: 10px; box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);">
        </div>

        <div class="section team">
            <h3>Tim Kami</h3>
            <div class="team-member">
                <img src="team_member1.jpg" alt="Anggota Tim 1">
                <h4>Nama Anggota 1</h4>
                <p>Peran di Perusahaan</p>
            </div>
            <div class="team-member">
                <img src="team_member2.jpg" alt="Anggota Tim 2">
                <h4>Nama Anggota 2</h4>
                <p>Peran di Perusahaan</p>
            </div>
            <div class="team-member">
                <img src="team_member3.jpg" alt="Anggota Tim 3">
                <h4>Nama Anggota 3</h4>
                <p>Peran di Perusahaan</p>
            </div>
        </div>

        <div class="section">
            <h3>Hubungi Kami</h3>
            <p>Jika Anda ingin mengetahui lebih lanjut tentang perusahaan atau layanan kami, silakan hubungi kami:</p>
            <form class="contact-form">
                <input type="text" placeholder="Nama" required>
                <input type="email" placeholder="Email" required>
                <textarea placeholder="Pesan" rows="4" required></textarea>
                <button type="submit">Kirim Pesan</button>
            </form>
            <p>Email: inspirasicemerlang.icm@gmail.com | Telepon: +62 853 4567 4445</p>
            <p>Alamat: Jl. Bendungan No. 95 Kab. Kolaka Sulawesi Tenggara</p>
        </div>

        <!-- Ikon Media Sosial -->
        <div class="social-icons">
            <a href="#"><i class="fab fa-whatsapp"></i></a>
            <a href="#"><i class="fab fa-instagram"></i></a>
            <a href="mailto:inspirasicemerlang.icm@gmail.com"><i class="fas fa-envelope"></i></a>
        </div>
    </div>

    <footer>
        <p>&copy; 2024 Inspirasi Cemerlang Mekongga. Semua hak dilindungi.</p>
        <p>Jam Operasional: Senin - Jumat, 09:00 - 17:00</p>
    </footer>

    <script>
        document.getElementById('nextButton').addEventListener('click', function() {
            document.querySelector('.container').style.animation = 'fadeOut 0.5s forwards';
            setTimeout(function() {
                document.querySelector('.container').style.display = 'none';
                document.getElementById('companyProfile').style.display = 'block';
            }, 500);
        });

        // Add keyframes for fadeOut
        const styleSheet = document.styleSheets[0];
        styleSheet.insertRule(`
            @keyframes fadeOut {
                from { opacity: 1; }
                to { opacity: 0; }
            }
        `, styleSheet.cssRules.length);
    </script>

</body>
</html>
