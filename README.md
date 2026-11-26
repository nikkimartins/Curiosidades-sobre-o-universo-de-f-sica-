<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Seletor de Código de Cor</title>
    <style>
        :root {
            --cor-fundo: #f4f4f9;
            --cor-cartao: #ffffff;
            --cor-texto: #333333;
        }

        body {
            font-family: Arial, sans-serif;
            background-color: var(--cor-fundo);
            color: var(--cor-texto);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        .cartao {
            background-color: var(--cor-cartao);
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            text-align: center;
            width: 320px;
        }

        input[type="color"] {
            width: 100%;
            height: 80px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            margin: 15px 0;
        }

        .codigos {
            background-color: #f0f0f5;
            padding: 15px;
            border-radius: 8px;
            font-family: monospace;
            font-size: 16px;
            line-height: 1.8;
        }
    </style>
</head>
<body>

    <div class="cartao">
        <h2>Escolha uma cor</h2>
        <input type="color" id="seletorCor" value="#3498db">
       
        <div class="codigos">
            <div><strong>HEX:</strong> <span id="valorHex">#3498db</span></div>
            <div><strong>RGB:</strong> <span id="valorRgb">rgb(52, 152, 219)</span></div>
        </div>
    </div>

    <script>
        const seletor = document.getElementById('seletorCor');
        const textoHex = document.getElementById('valorHex');
        const textoRgb = document.getElementById('valorRgb');

        seletor.addEventListener('input', (evento) => {
            const hex = evento.target.value;
            textoHex.textContent = hex.toUpperCase();

            // Converte HEX para RGB
            const r = parseInt(hex.slice(1, 3), 16);
            const g = parseInt(hex.slice(3, 5), 16);
            const b = parseInt(hex.slice(5, 7), 16);
            textoRgb.textContent = `rgb(${r}, ${g}, ${b})`;
        });
    </script>

</body>
</html>

