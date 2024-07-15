# almostfreepixels
git init
git add index.html
git commit -m "Initial commit"
git remote add origin https://github.com/<elcocoricoo>/<almostfreepixels>.git
git branch -M main
git push -u origin main
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vente de Pixels</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }
        .container {
            width: 1000px;
            margin: 0 auto;
        }
        #pixel-grid {
            display: grid;
            grid-template-columns: repeat(1000, 1px);
            grid-template-rows: repeat(1000, 1px);
            gap: 1px;
            margin: 20px 0;
        }
        .pixel {
            width: 1px;
            height: 1px;
            background-color: #e0e0e0;
        }
    </style>
</head>
<body>
    <h1>Vente de Pixels</h1>
    <p>Achetez des pixels au prix de 0,10 € chacun.</p>
    <form id="purchase-form">
        <label for="quantity">Quantité de pixels :</label>
        <input type="number" id="quantity" name="quantity" min="1" max="1000000" required>
        <button type="submit">Acheter</button>
    </form>
    <div class="container">
        <div id="pixel-grid"></div>
    </div>

    <script>
        const pixelGrid = document.getElementById('pixel-grid');
        const purchaseForm = document.getElementById('purchase-form');

        for (let i = 0; i < 1000000; i++) {
            const pixel = document.createElement('div');
            pixel.classList.add('pixel');
            pixelGrid.appendChild(pixel);
        }

        purchaseForm.addEventListener('submit', function(event) {
            event.preventDefault();
            const quantity = parseInt(document.getElementById('quantity').value);
            const cost = quantity * 0.10;
            alert(`Vous avez acheté ${quantity} pixels pour un total de ${cost.toFixed(2)} €.`);
            for (let i = 0; i < quantity; i++) {
                const pixel = pixelGrid.children[i];
                pixel.style.backgroundColor = '#000000';
            }
        });
    </script>
</body>
</html>
