<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cosmos | Exploración Espacial</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: Arial, Helvetica, sans-serif;
            color: white;
            background: #050816;
            overflow-x: hidden;
        }

        /* Fondo de estrellas */
        body::before {
            content: "";
            position: fixed;
            inset: 0;
            z-index: -2;
            background:
                radial-gradient(circle at 20% 30%, #332080 0, transparent 25%),
                radial-gradient(circle at 80% 70%, #0b4f87 0, transparent 25%),
                #050816;
        }

        body::after {
            content: "";
            position: fixed;
            inset: 0;
            z-index: -1;
            opacity: .5;
            background-image:
                radial-gradient(white 1px, transparent 1px),
                radial-gradient(white 1px, transparent 1px);
            background-size: 100px 100px, 170px 170px;
            background-position: 20px 30px, 70px 90px;
        }

        /* Navegación */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 20px 8%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(5, 8, 22, .7);
            backdrop-filter: blur(12px);
            z-index: 100;
            border-bottom: 1px solid rgba(255,255,255,.08);
        }

        .logo {
            font-size: 25px;
            font-weight: bold;
            color: #8be9fd;
        }

        nav ul {
            display: flex;
            gap: 30px;
            list-style: none;
        }

        nav a {
            color: white;
            text-decoration: none;
            transition: .3s;
        }

        nav a:hover {
            color: #8be9fd;
        }

        /* Hero */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 100px 20px 50px;
        }

        .hero-content {
            max-width: 850px;
        }

        .hero h1 {
            font-size: clamp(50px, 9vw, 100px);
            line-height: .95;
            margin-bottom: 25px;
            background: linear-gradient(90deg, #fff, #8be9fd, #bd93f9);
            -webkit-background-clip: text;
            color: transparent;
        }

        .hero p {
            font-size: 20px;
            color: #c9d2e8;
            line-height: 1.7;
            margin-bottom: 35px;
        }

        .btn {
            display: inline-block;
            padding: 15px 30px;
            border-radius: 50px;
            background: linear-gradient(90deg, #6c5ce7, #00bfff);
            color: white;
            text-decoration: none;
            font-weight: bold;
            transition: .3s;
            box-shadow: 0 0 25px rgba(0,191,255,.25);
        }

        .btn:hover {
            transform: translateY(-4px) scale(1.03);
            box-shadow: 0 0 35px rgba(0,191,255,.5);
        }

        /* Secciones */
        section {
            padding: 100px 8%;
        }

        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }

        .section-title h2 {
            font-size: 42px;
            margin-bottom: 10px;
        }

        .section-title p {
            color: #9da9c2;
        }

        /* Tarjetas */
        .cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
            gap: 25px;
        }

        .card {
            padding: 30px;
            background: rgba(255,255,255,.06);
            border: 1px solid rgba(255,255,255,.1);
            border-radius: 20px;
            backdrop-filter: blur(10px);
            transition: .3s;
        }

        .card:hover {
            transform: translateY(-10px);
            border-color: #8be9fd;
            box-shadow: 0 15px 40px rgba(0,0,0,.3);
        }

        .icon {
            font-size: 45px;
            margin-bottom: 20px;
        }

        .card h3 {
            font-size: 24px;
            margin-bottom: 12px;
        }

        .card p {
            color: #aeb9d0;
            line-height: 1.6;
        }

        /* Estadísticas */
        .stats {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
            max-width: 900px;
            margin: auto;
        }

        .stat {
            text-align: center;
            padding: 35px;
            border-radius: 20px;
            background: linear-gradient(
                145deg,
                rgba(108,92,231,.2),
                rgba(0,191,255,.08)
            );
        }

        .stat strong {
            display: block;
            font-size: 45px;
            color: #8be9fd;
            margin-bottom: 10px;
        }

        .stat span {
            color: #b5c0d7;
        }

        /* CTA */
        .cta {
            text-align: center;
            margin: 50px auto;
            max-width: 900px;
            padding: 70px 30px;
            border-radius: 30px;
            background:
                linear-gradient(
                    135deg,
                    rgba(108,92,231,.25),
                    rgba(0,191,255,.15)
                );
            border: 1px solid rgba(255,255,255,.1);
        }

        .cta h2 {
            font-size: 40px;
            margin-bottom: 20px;
        }

        .cta p {
            color: #c0c9dc;
            margin-bottom: 30px;
        }

        footer {
            text-align: center;
            padding: 35px;
            color: #76819a;
            border-top: 1px solid rgba(255,255,255,.08);
        }

        /* Responsive */
        @media (max-width: 700px) {
            nav ul {
                display: none;
            }

            .stats {
                grid-template-columns: 1fr;
            }

            section {
                padding: 75px 6%;
            }
        }
    </style>
</head>

<body>

    <nav>
        <div class="logo">🚀 COSMOS</div>

        <ul>
            <li><a href="#inicio">Inicio</a></li>
            <li><a href="#planetas">Planetas</a></li>
            <li><a href="#datos">Datos</a></li>
        </ul>
    </nav>

    <main>

        <section class="hero" id="inicio">
            <div class="hero-content">
                <h1>Explora el Cosmos</h1>

                <p>
                    El universo es mucho más grande de lo que podemos imaginar.
                    Descubre planetas, estrellas, galaxias y los misterios que
                    todavía esperan ser descubiertos.
                </p>

                <a href="#planetas" class="btn">
                    Comenzar exploración →
                </a>
            </div>
        </section>

        <section id="planetas">

            <div class="section-title">
                <h2>🌌 Mundos increíbles</h2>
                <p>Algunos de los lugares más fascinantes de nuestro universo.</p>
            </div>

            <div class="cards">

                <article class="card">
                    <div class="icon">🌍</div>
                    <h3>La Tierra</h3>
                    <p>
                        Nuestro hogar. Un planeta lleno de océanos, montañas,
                        vida y una increíble diversidad de ecosistemas.
                    </p>
                </article>

                <article class="card">
                    <div class="icon">🔴</div>
                    <h3>Marte</h3>
                    <p>
                        El planeta rojo. Los científicos estudian su superficie
                        para descubrir si alguna vez pudo albergar vida.
                    </p>
                </article>

                <article class="card">
                    <div class="icon">🪐</div>
                    <h3>Saturno</h3>
                    <p>
                        Un gigante gaseoso famoso por sus impresionantes anillos
                        formados principalmente por hielo y roca.
                    </p>
                </article>

                <article class="card">
                    <div class="icon">✨</div>
                    <h3>Exoplanetas</h3>
                    <p>
                        Mundos que orbitan otras estrellas. Algunos podrían tener
                        condiciones interesantes para la vida.
                    </p>
                </article>

            </div>
        </section>

        <section id="datos">

            <div class="section-title">
                <h2>📡 El universo en números</h2>
                <p>Algunas cifras para dimensionar nuestro cosmos.</p>
            </div>

            <div class="stats">

                <div class="stat">
                    <strong>8</strong>
                    <span>Planetas principales del Sistema Solar</span>
                </div>

                <div class="stat">
                    <strong>1</strong>
                    <span>Estrella en nuestro Sistema Solar</span>
                </div>

                <div class="stat">
                    <strong>∞</strong>
                    <span>Preguntas todavía sin responder</span>
                </div>

            </div>

        </section>

        <section>
            <div class="cta">
                <h2>El universo te está esperando 🚀</h2>

                <p>
                    Mira hacia las estrellas. Quizás el próximo gran descubrimiento
                    comience con tu curiosidad.
                </p>

                <a href="#inicio" class="btn">
                    Volver arriba ↑
                </a>
            </div>
        </section>

    </main>

    <footer>
        <p>© 2026 COSMOS — Página creada en HTML y CSS.</p>
    </footer>

</body>
</html>
