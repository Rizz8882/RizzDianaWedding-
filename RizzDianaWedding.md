<html lang="ms">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jemputan Perkahwinan Rizz & Diana</title>
    <style>
        /* Reka Bentuk Global */
        body {
            font-family: 'Georgia', serif;
            background: linear-gradient(to right, #f8e6b7, #eac17a);
            text-align: center;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        /* Kotak Jemputan */
        .invitation {
            background: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            animation: fadeIn 1.5s ease-in-out;
            max-width: 400px;
        }

        h1 { color: #b68d40; font-size: 24px; }
        h2 { color: #8d6a2c; font-size: 28px; }
        p { font-size: 16px; color: #444; margin: 10px 0; }
        .hadith { font-style: italic; color: #6b4f24; margin-top: 15px; }

        /* Butang */
        button {
            background: #b68d40;
            color: white;
            padding: 12px 20px;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            cursor: pointer;
            margin-top: 15px;
            transition: 0.3s;
        }
        button:hover { background: #8d6a2c; }

        /* Animasi */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(-20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Pop-up RSVP */
        .popup {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            justify-content: center;
            align-items: center;
        }

        .popup-content {
            background: white;
            padding: 20px;
            border-radius: 8px;
            text-align: center;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            width: 300px;
        }

        input {
            width: 90%;
            padding: 10px;
            margin-top: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <div class="invitation">
        <h1>Majlis Perkahwinan</h1>
        <h2>Rizz & Diana</h2>
        <p>Dengan penuh kesyukuran, kami menjemput anda ke majlis perkahwinan kami.</p>
        <p><strong>Tarikh:</strong> 5 Julai 2025</p>
        <p><strong>Lokasi:</strong> Bangi Guest House</p>
        <p class="hadith">"Perkahwinan itu adalah sebahagian daripada sunnahku" – Hadis Riwayat Ibnu Majah</p>
        <button onclick="openRSVP()">RSVP Sekarang</button>
    </div>

    <!-- Pop-up RSVP -->
    <div id="rsvpPopup" class="popup">
        <div class="popup-content">
            <h3>Sahkan Kehadiran Anda</h3>
            <input type="text" id="name" placeholder="Nama Anda">
            <button onclick="submitRSVP()">Hantar</button>
            <button onclick="closeRSVP()">Tutup</button>
        </div>
    </div>

    <script>
        function openRSVP() {
            document.getElementById("rsvpPopup").style.display = "flex";
        }

        function closeRSVP() {
            document.getElementById("rsvpPopup").style.display = "none";
        }

        function submitRSVP() {
            let name = document.getElementById("name").value;
            if (name.trim() === "") {
                alert("Sila masukkan nama anda.");
            } else {
                alert("Terima kasih " + name + "! Kehadiran anda telah disahkan.");
                closeRSVP();
            }
        }
    </script>
</body>
</html>
<!-- Pemain Muzik Selawat -->
<audio id="selawatAudio" autoplay loop>
    <source src="LINK_AUDIO_SELAWAT.mp3" type="audio/mpeg">
    Browser anda tidak menyokong audio.
</audio>

<!-- Butang Kawalan Muzik -->
<button id="musicButton" onclick="toggleMusic()">🔊 Mainkan Selawat</button>

<script>
    let audio = document.getElementById("selawatAudio");
    let musicButton = document.getElementById("musicButton");

    // Mulakan dengan volume rendah untuk elak sekatan
    window.addEventListener('load', function() {
        audio.volume = 0.5; // Tetapkan volume awal
        audio.play().catch(() => {
            console.log("Autoplay disekat, perlu interaksi pengguna.");
        });
    });

    function toggleMusic() {
        if (audio.paused) {
            audio.play();
            musicButton.innerHTML = "⏸ Hentikan Selawat";
        } else {
            audio.pause();
            musicButton.innerHTML = "🔊 Mainkan Selawat";
        }
    }
</script>
