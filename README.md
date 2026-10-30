# Pago-nfc
Ventana que muestra datos para realizar transferencias 
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Datos de pago</title>

    <style>
        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
            background: #f4f4f4;
            color: #171717;
        }

        .container {
            max-width: 430px;
            margin: auto;
            padding: 25px 18px;
        }

        .card {
            background: white;
            border-radius: 24px;
            padding: 28px 22px;
            box-shadow: 0 8px 30px rgba(0,0,0,0.08);
        }

        .logo {
            width: 75px;
            height: 75px;
            border-radius: 18px;
            object-fit: cover;
            display: block;
            margin: 0 auto 15px;
        }

        h1 {
            text-align: center;
            margin: 5px 0;
            font-size: 25px;
        }

        .subtitle {
            text-align: center;
            color: #777;
            margin-bottom: 28px;
        }

        .data {
            margin-bottom: 18px;
        }

        .label {
            font-size: 12px;
            color: #777;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 5px;
        }

        .value {
            font-size: 17px;
            font-weight: 600;
            word-break: break-word;
        }

        button {
            width: 100%;
            border: none;
            border-radius: 12px;
            padding: 13px;
            margin-top: 8px;
            background: #171717;
            color: white;
            font-size: 15px;
            font-weight: 600;
            cursor: pointer;
        }

        .whatsapp {
            background: #25D366;
            margin-top: 20px;
        }

        .message {
            text-align: center;
            color: #25a244;
            font-size: 13px;
            margin-top: 8px;
            height: 18px;
        }

        .footer {
            text-align: center;
            font-size: 11px;
            color: #999;
            margin-top: 20px;
        }
    </style>
</head>

<body>

<div class="container">

    <div class="card">

        <!-- LOGO -->
        <img
            class="logo"
            src="https://via.placeholder.com/150"
            alt="Logo"
        >

        <!-- NOMBRE DEL NEGOCIO -->
        <h1>FLORERIA</h1>

        <div class="subtitle">
            Datos para transferencia
        </div>


        <!-- BANCO -->
        <div class="data">
            <div class="label">Banco</div>
            <div class="value">NU</div>
        </div>


        <!-- TITULAR -->
        <div class="data">
            <div class="label">Titular</div>
            <div class="value">
                KARLA XIMENA CANALES
            </div>
        </div>


        <!-- CLABE -->
        <div class="data">
            <div class="label">CLABE interbancaria</div>

            <div class="value" id="clabe">
                5101254721364099
            </div>

            <button onclick="copiar('clabe')">
                COPIAR CLABE
            </button>

            <div class="message" id="mensaje-clabe"></div>
        </div>


        <!-- CUENTA -->
        <div class="data">
            <div class="label">Número de cuenta</div>

            <div class="value" id="cuenta">
                
            </div>

            <button onclick="copiar('cuenta')">
                COPIAR CUENTA
            </button>

            <div class="message" id="mensaje-cuenta"></div>
        </div>


        <!-- WHATSAPP -->
        <button
            class="whatsapp"
            onclick="window.open('https://wa.me/+52 55 6368 0395', '_blank')"
        >
            CONTACTAR POR WHATSAPP
        </button>


        <div class="footer">
            Página creada por GEC Nexus
        </div>

    </div>

</div>


<script>

function copiar(id) {

    const texto = document.getElementById(id).innerText;

    navigator.clipboard.writeText(texto).then(function() {

        if (id === "clabe") {
            document.getElementById("mensaje-clabe").innerText =
                "✓ CLABE copiada";
        }

        if (id === "cuenta") {
            document.getElementById("mensaje-cuenta").innerText =
                "✓ Cuenta copiada";
        }

    });

}

</script>

</body>
</html>
