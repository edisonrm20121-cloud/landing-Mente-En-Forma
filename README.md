<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MenteEnForma / NeuroGym Co. - Landing Page</title>
    <style>
        /* ==========================================================================
           1. VARIABLES DE DISEÑO (Paleta de colores 50-40-10 y Tipografía)
           ========================================================================== */
        :root {
            --NEGRO: #1a3644;  /* 50% - Color dominante/fondo principal */
            --azul-claro: #254d60;     /* Variación para contrastes secundarios */
            --verde-sabio: #87a987;    /* 40% - Color secundario para textos/estructuras */
            --verde-claro: #f4f7f4;    /* Fondo claro para legibilidad */
            --coral-calido: #e06d53;   /* 10% - Color de acento para CTA y destaques */
            --blanco: #ffffff;
            --texto-oscuro: #222222;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--verde-claro);
            color: var(--texto-oscuro);
            line-height: 1.6;
        }

        /* Enlaces globales */
        a {
            text-decoration: none;
            color: inherit;
        }

        /* Contenedor auxiliar para centrar contenido */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* ==========================================================================
           2. ENCABEZADO (Header)
           ========================================================================== */
        .header {
            background-color: var(--azul-petroleo);
            color: var(--blanco);
            padding: 20px 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.2);
        }

        .header .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--verde-sabio);
        }

        .logo span {
            color: var(--coral-calido);
        }

        .nav-menu {
            display: flex;
            list-style: none;
            gap: 20px;
        }

        .nav-menu a {
            font-weight: 500;
            transition: color 0.3s;
        }

        .nav-menu a:hover {
            color: var(--coral-calido);
        }

        /* ==========================================================================
           3. SECCIÓN PRINCIPAL (Hero Section)
           ========================================================================== */
        .hero {
            background: linear-gradient(135deg, var(--azul-petroleo) 0%, var(--azul-claro) 100%);
            color: var(--blanco);
            padding: 100px 0;
            text-align: center;
        }

        .hero h1 {
            font-size: 2.8rem;
            margin-bottom: 20px;
            color: var(--blanco);
            max-width: 900px;
            margin-left: auto;
            margin-right: auto;
        }

        .hero p {
            font-size: 1.2rem;
            color: var(--verde-sabio);
            margin-bottom: 40px;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }

        /* Botón de Acción Principal (CTA) */
        .btn-cta {
            background-color: var(--coral-calido);
            color: var(--blanco);
            padding: 15px 35px;
            font-size: 1.1rem;
            font-weight: bold;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: transform 0.2s, background-color 0.3s;
            box-shadow: 0 4px 15px rgba(224, 109, 83, 0.4);
        }

        .btn-cta:hover {
            background-color: #d15c42;
            transform: translateY(-2px);
        }

        /* ==========================================================================
           4. TARJETAS DE SERVICIOS (El Entrenamiento Mental)
           ========================================================================== */
        .services {
            padding: 80px 0;
            background-color: var(--blanco);
        }

        .section-title {
            text-align: center;
            font-size: 2.2rem;
            margin-bottom: 50px;
            color: var(--azul-petroleo);
            position: relative;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 60px;
            height: 4px;
            background-color: var(--coral-calido);
            margin: 10px auto 0 auto;
            border-radius: 2px;
        }

        .grid-services {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .card {
            background-color: var(--verde-claro);
            padding: 40px 30px;
            border-radius: 8px;
            border-top: 5px solid var(--verde-sabio);
            box-shadow: 0 4px 6px rgba(0,0,0,0.05);
            transition: transform 0.3s;
        }

        .card:hover {
            transform: translateY(-5px);
        }

        .card h3 {
            color: var(--azul-petroleo);
            margin-bottom: 15px;
            font-size: 1.4rem;
        }

        /* ==========================================================================
           5. SECCIÓN DE PLANES (Enfoque Comercial)
           ========================================================================== */
        .pricing {
            padding: 80px 0;
            background-color: var(--verde-claro);
        }

        .grid-pricing {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            align-items: stretch;
        }

        .price-card {
            background-color: var(--blanco);
            border-radius: 8px;
            padding: 40px 30px;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0,0,0,0.05);
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            position: relative;
        }

        /* Resaltado para el plan recomendado (Premium) */
        .price-card.featured {
            border: 2px solid var(--coral-calido);
            transform: scale(1.03);
            background-color: #fcfaf9;
        }

        .badge {
            position: absolute;
            top: -15px;
            left: 50%;
            transform: translateX(-50%);
            background-color: var(--coral-calido);
            color: var(--blanco);
            padding: 5px 15px;
            font-size: 0.8rem;
            font-weight: bold;
            border-radius: 20px;
            text-transform: uppercase;
        }

        .price-card h3 {
            color: var(--azul-petroleo);
            font-size: 1.5rem;
            margin-bottom: 15px;
        }

        .price {
            font-size: 2.5rem;
            font-weight: bold;
            color: var(--azul-petroleo);
            margin-bottom: 25px;
        }

        .price span {
            font-size: 1rem;
            color: #666;
        }

        .features-list {
            list-style: none;
            text-align: left;
            margin-bottom: 35px;
        }

        .features-list li {
            margin-bottom: 12px;
            padding-left: 25px;
            position: relative;
        }

        /* Checkmarks personalizados con CSS nativo */
        .features-list li::before {
            content: '✓';
            position: absolute;
            left: 0;
            color: var(--verde-sabio);
            font-weight: bold;
        }

        .price-card.featured .features-list li::before {
            color: var(--coral-calido);
        }

        /* ==========================================================================
           6. FORMULARIO DE CAPTACIÓN (Lead Magnet) y MENSAJES
           ========================================================================== */
        .contact-section {
            padding: 80px 0;
            background-color: var(--blanco);
        }

        .form-container {
            max-width: 600px;
            margin: 0 auto;
            background-color: var(--verde-claro);
            padding: 40px;
            border-radius: 8px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.05);
        }

        .form-container p {
            text-align: center;
            margin-bottom: 30px;
            color: #555;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--azul-petroleo);
        }

        .form-control {
            width: 100%;
            padding: 12px;
            border: 1px solid #ccc;
            border-radius: 4px;
            font-size: 1rem;
            background-color: var(--blanco);
        }

        .form-control:focus {
            outline: none;
            border-color: var(--azul-petroleo);
            box-shadow: 0 0 5px rgba(26, 54, 68, 0.3);
        }

        /* Contenedores para mensajes dinámicos de JS */
        .msg-container {
            margin-top: 20px;
            padding: 15px;
            border-radius: 5px;
            display: none; /* Se activa con JS */
            font-weight: 500;
        }

        .msg-success-sistema {
            background-color: #d4edda;
            color: #155724;
            border: 1px solid #c3e6cb;
        }

        .msg-neuron-action {
            background-color: #e8f4f8;
            color: var(--azul-petroleo);
            border-left: 5px solid var(--coral-calido);
            margin-top: 15px;
        }

        /* ==========================================================================
           7. PIE DE PÁGINA (Footer)
           ========================================================================== */
        .footer {
            background-color: var(--azul-petroleo);
            color: var(--blanco);
            padding: 40px 0;
            font-size: 0.9rem;
            border-top: 3px solid var(--coral-calido);
        }

        .footer .container {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            flex-wrap: wrap;
            gap: 30px;
        }

        .footer-col h4 {
            color: var(--verde-sabio);
            margin-bottom: 15px;
            font-size: 1.1rem;
        }

        .footer-col p {
            margin-bottom: 8px;
            color: #cbd5e1;
        }

        .footer-bottom {
            width: 100%;
            text-align: center;
            margin-top: 30px;
            padding-top: 20px;
            border-top: 1px solid rgba(255,255,255,0.1);
            color: #94a3b8;
        }

        /* ==========================================================================
           8. RESPONSIVE DESIGN (Media Queries)
           ========================================================================== */
        @media (max-width: 768px) {
            .header .container {
                flex-direction: column;
                gap: 15px;
            }
            .hero h1 {
                font-size: 2rem;
            }
            .price-card.featured {
                transform: scale(1); /* Evitamos distorsión en pantallas chicas */
            }
            .footer .container {
                flex-direction: column;
                text-align: center;
                align-items: center;
            }
        }
    </style>
</head>
<body>

    <!-- 1. ENCABEZADO -->
    <header class="header">
        <div class="container">
            <div class="logo">MenteEnForma / <span>NeuroGym Co.</span></div>
            <nav>
                <ul class="nav-menu">
                    <li><a href="#inicio">Inicio</a></li>
                    <li><a href="#metodo">El Método</a></li>
                    <li><a href="#planes">Planes</a></li>
                    <li><a href="#contacto">Contacto</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- 2. SECCIÓN PRINCIPAL (HERO) -->
    <section id="inicio" class="hero">
        <div class="container">
            <h1>Entrena tu mente, reprograma tu progreso y reserva tus sesiones de mentoría desde una sola plataforma</h1>
            <p>Conecta la neurociencia con la meditación diaria y desbloquea el siguiente nivel de tu crecimiento personal.</p>
            <button class="btn-cta" onclick="scrollAlFormulario()">Empezar mi Transformación</button>
        </div>
    </section>

    <!-- 3. TARJETAS DE SERVICIOS -->
    <section id="metodo" class="services">
        <div class="container">
            <h2 class="section-title">El Entrenamiento Mental</h2>
            <div class="grid-services">
                <div class="card">
                    <h3>Membresías de Enfoque</h3>
                    <p>Acceso ilimitado a nuestra biblioteca de neuro-meditaciones guiadas y herramientas de biohacking mental.</p>
                </div>
                <div class="card">
                    <h3>Rutinas Neuro-Personalizadas</h3>
                    <p>Planes de hábitos diseñados a la medida de tu mapa cerebral y tus objetivos de productividad o paz mental.</p>
                </div>
                <div class="card">
                    <h3>Sesiones Grupales de Co-Creación</h3>
                    <p>Clases en vivo de meditación avanzada y dinámicas de crecimiento personal con nuestra comunidad global.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- 4. SECCIÓN DE PLANES -->
    <section id="planes" class="pricing">
        <div class="container">
            <h2 class="section-title">Nuestros Planes</h2>
            <div class="grid-pricing">
                <!-- Plan Básico -->
                <div class="price-card">
                    <div>
                        <h3>Plan Básico (Iniciación)</h3>
                        <div class="price">€19<span>/mes</span></div>
                        <ul class="features-list">
                            <li>Acceso a meditaciones base.</li>
                            <li>Seguimiento de progreso estándar.</li>
                            <li>Soporte por comunidad.</li>
                        </ul>
                    </div>
                    <button class="btn-cta" style="width:100%;" onclick="seleccionarPlan('Básico')">Elegir Plan</button>
                </div>

                <!-- Plan Premium (Destaque) -->
                <div class="price-card featured">
                    <div class="badge">Recomendado</div>
                    <div>
                        <h3>Plan Premium (Superhábito) ★</h3>
                        <div class="price">€49<span>/mes</span></div>
                        <ul class="features-list">
                            <li><strong>Plan Meditación Plus: Crea tu Superhábito.</strong></li>
                            <li>Mentoría semanal + Plantillas de neuro-hábitos.</li>
                            <li>Soporte prioritario 1:1.</li>
                        </ul>
                    </div>
                    <button class="btn-cta" style="width:100%;" onclick="seleccionarPlan('Premium')">Elegir Premium</button>
                </div>

                <!-- Plan Familiar -->
                <div class="price-card">
                    <div>
                        <h3>Familiar / Corporativo</h3>
                        <div class="price">€99<span>/mes</span></div>
                        <ul class="features-list">
                            <li>Hasta 4 cuentas activas.</li>
                            <li>Todo lo del Plan Premium para el grupo.</li>
                            <li>Sesión mensual grupal exclusiva.</li>
                        </ul>
                    </div>
                    <button class="btn-cta" style="width:100%;" onclick="seleccionarPlan('Familiar')">Elegir Familiar</button>
                </div>
            </div>
        </div>
    </section>

    <!-- 5 Y 6. FORMULARIO DE CAPTACIÓN Y LÓGICA INTERACTIVA -->
    <section id="contacto" class="contact-section">
        <div class="container">
            <h2 class="section-title">¿Listo para reprogramar tu mente?</h2>
            <div class="form-container">
                <p>Déjanos tus datos y un neuro-coach te guiará para elegir tu camino ideal.</p>
                
                <form id="leadForm" onsubmit="procesarFormulario(event)">
                    <div class="form-group">
                        <label for="nombre">Nombre Completo</label>
                        <input type="text" id="nombre" class="form-control" placeholder="Ej. Juan Pérez">
                    </div>
                    
                    <div class="form-group">
                        <label for="correo">Correo Electrónico</label>
                        <input type="email" id="correo" class="form-control" placeholder="Ej. juan@correo.com">
                    </div>
                    
                    <div class="form-group">
                        <label for="plan">Plan de interés</label>
                        <select id="plan" class="form-control">
                            <option value="">-- Selecciona un plan --</option>
                            <option value="Básico">Básico</option>
                            <option value="Premium">Premium: Meditación Plus</option>
                            <option value="Familiar">Familiar / Corporativo</option>
                        </select>
                    </div>
                    
                    <button type="submit" class="btn-cta" style="width: 100%; margin-top: 10px;">
                        ¡Quiero mi Plan Meditación Plus!
                    </button>
                </form>

                <!-- Contenedores ocultos donde insertaremos las respuestas dinámicas mediante JS -->
                <div id="sistemaFeedback" class="msg-container msg-success-sistema"></div>
                <div id="simulacionFeedback" class="msg-container msg-neuron-action"></div>
            </div>
        </div>
    </section>

    <!-- 7. PIE DE PÁGINA -->
    <footer class="footer">
        <div class="container">
            <div class="footer-col">
                <h4>Contacto</h4>
                <p>Email: info@menteenforma.com</p>
                <p>Teléfono: +34 600 000 000</p>
            </div>
            <div class="footer-col">
                <h4>Redes Sociales</h4>
                <p>Instagram / TikTok: @MenteEnForma.Neuro</p>
            </div>
            <div class="footer-col">
                <h4>Filosofía</h4>
                <p>Entrenamiento mental basado en evidencia científica.</p>
            </div>
            <div class="footer-bottom">
                <p>Legales: © 2026 MenteEnForma. Conectando ciencia y espiritualidad. Todos los derechos reservados.</p>
            </div>
        </div>
    </footer>

    <!-- ==========================================================================
       9. LÓGICA DE PROGRAMACIÓN (JavaScript)
       ========================================================================== */ -->
    <script>
        /**
         * Función para hacer scroll suave directo al formulario al pulsar el botón del Hero
         */
        function scrollAlFormulario() {
            document.getElementById('contacto').scrollIntoView({ behavior: 'smooth' });
        }

        /**
         * Permite que al dar clic a "Elegir Plan" en la sección comercial, 
         * el selector del formulario se cambie automáticamente.
         */
        function seleccionarPlan(nombrePlan) {
            const selectPlan = document.getElementById('plan');
            selectPlan.value = nombrePlan;
            scrollAlFormulario();
        }

        /**
         * Controlador del evento Submit del formulario.
         * Se encarga de validar los datos del DOM y renderizar los feedbacks solicitados.
         */
        function procesarFormulario(event) {
            // Evitamos que la página se recargue (comportamiento por defecto del submit)
            event.preventDefault();

            // Captura de nodos/elementos del DOM
            const nombre = document.getElementById('nombre').value.trim();
            const correo = document.getElementById('correo').value.trim();
            const planSeleccionado = document.getElementById('plan').value;
            
            const contenedorSistema = document.getElementById('sistemaFeedback');
            const contenedorSimulacion = document.getElementById('simulacionFeedback');

            // Limpieza previa de contenedores por si el usuario re-envía el formulario
            contenedorSistema.style.display = 'none';
            contenedorSimulacion.style.display = 'none';

            // ESTRATEGIA DE VALIDACIÓN: Validación de presencia básica
            if (nombre === "" || correo === "") {
                alert("Por favor, completa los campos de Nombre y Correo Electrónico antes de continuar.");
                return; // Rompe el flujo de ejecución si hay campos vacíos
            }

            // Si pasa la validación, procedemos con la lógica de negocio simulada:
            
            // 1. Mensaje de procesamiento interno solicitado por el requerimiento didáctico
            contenedorSistema.innerText = "Solicitud enviada correctamente. Un asesor se comunicará contigo.";
            contenedorSistema.style.display = 'block';

            // 2. Mensaje comercial simulado de conversión
            contenedorSimulacion.innerHTML = `<strong>¡Neuronas en acción! 🧠</strong> Tu solicitud ha sido procesada con éxito. En menos de 24 horas recibirás en tu correo el acceso al test de neuro-perfil y los detalles de tu Plan Meditación Plus. ¡Prepárate para crear tu superhábito!`;
            contenedorSimulacion.style.display = 'block';

            // Opcional: Resetear el formulario tras el envío exitoso
            document.getElementById('leadForm').reset();
        }
    </script>
</body>
</html>
