<!DOCTYPE html><html lang="tr"><head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Uzun Kodlu İşlem Paneli</title>
    <style>
        /* Arka plan animasyonu */
        @keyframes backgroundAnimation {
            0% { background-color: #ff7e5f; }
            25% { background-color: #feb47b; }
            50% { background-color: #88d8b0; }
            75% { background-color: #0e0c1b; }
            100% { background-color: #ff7e5f; }
        }body {
        animation: backgroundAnimation 5s ease infinite;
        font-family: 'Arial', sans-serif;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        height: 100vh;
        text-align: center;
        color: white;
        margin: 0;
        padding: 0;
    }

    h1, h2 {
        margin: 10px 0;
        padding: 10px;
    }

    input, textarea, button {
        padding: 15px;
        margin: 10px;
        width: 300px;
        font-size: 16px;
        border: none;
        border-radius: 5px;
        transition: background-color 0.3s ease;
    }

    input, textarea {
        background-color: rgba(255, 255, 255, 0.2);
        color: white;
    }

    button {
        background-color: #ff4757;
        color: white;
        cursor: pointer;
    }

    button:hover {
        background-color: #e84118;
    }

    #inputForm {
        border: 1px solid white;
        border-radius: 10px;
        padding: 20px;
        box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
        background-color: rgba(0, 0, 0, 0.7);
        opacity: 0.9;
    }

    #details {
        margin-top: 20px;
        padding: 15px;
        border: 2px solid white;
        border-radius: 10px;
        background-color: rgba(255, 255, 255, 0.1);
        opacity: 0;
        transition: opacity 1s ease;
        white-space: pre-wrap;
        color: white;
    }
</style>

</head><body>
    <h1>Uzun Kodlu İşlem Paneli</h1>
    <div id="inputForm">
        <h2>İşlem Bilgilerini Girin</h2>
        <input type="text" id="ip" placeholder="Geçerli IP Adresi" required>
        <textarea id="code" placeholder="Buraya kodu yazın..." rows="6" cols="30" required></textarea>
        <input type="number" id="portCount" placeholder="Açılacak Port Sayısı" min="1" required>
        <input type="number" id="duration" placeholder="Süre (saniye)" min="1" required>
        <button id="crashButton">Crash</button>
        <div id="details"></div>
    </div><script>
    document.getElementById('crashButton').addEventListener('click', function () {
        const ip = document.getElementById('ip').value.trim();
        const code = document.getElementById('code').value.trim();
        const portCount = parseInt(document.getElementById('portCount').value, 10);
        const duration = parseInt(document.getElementById('duration').value, 10);

        if (!ip || !code || isNaN(portCount) || isNaN(duration)) {
            alert('Lütfen tüm alanları doldurun.');
            return;
        }

        const detailsDiv = document.getElementById('details');
        detailsDiv.innerHTML = `
            <strong>İşlem Başlatıldı:</strong><br>
            IP: ${ip}<br>
            Kod: ${code}<br>
            Port Sayısı: ${portCount}<br>
            Süre: ${duration} saniye
        `;
        detailsDiv.style.opacity = '1';
    });
</script>

</body></html>
