<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ODS en Acción: Un Llamamiento Global</title>
    <!-- Carga de Tailwind CSS para un diseño moderno y responsivo -->
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;800&display=swap" rel="stylesheet">
    <style>
        /* Estilos personalizados para la paleta de colores de los ODS */
        :root {
            --color-1: #e5243b; /* Fin de la Pobreza */
            --color-2: #dda63a; /* Hambre Cero */
            --color-3: #4c9f38; /* Salud y Bienestar */
            --color-4: #c5192d; /* Educación de Calidad */
            --color-5: #ff3a21; /* Igualdad de Género */
            --color-6: #26bde2; /* Agua Limpia y Saneamiento */
            --color-7: #fcc30b; /* Energía Asequible y No Contaminante */
            --color-8: #a21942; /* Trabajo Decente y Crecimiento Económico */
            --color-9: #fd6925; /* Industria, Innovación e Infraestructura */
            --color-10: #dd1367; /* Reducción de las Desigualdades */
            --color-11: #fd9d24; /* Ciudades y Comunidades Sostenibles */
            --color-12: #bf8b2e; /* Producción y Consumo Responsables */
            --color-13: #3f7e44; /* Acción por el Clima */
            --color-14: #0a97d9; /* Vida Submarina */
            --color-15: #50974b; /* Vida de Ecosistemas Terrestres */
            --color-16: #56c02b; /* Paz, Justicia e Instituciones Sólidas */
            --color-17: #19486a; /* Alianzas para Lograr los Objetivos */
        }
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f8f9fa;
        }
        .ods-card {
            transition: transform 0.3s, box-shadow 0.3s;
        }
        .ods-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }
        .ods-header {
            background-color: var(--color-17);
        }
        .ods-goal-icon {
            font-size: 2.5rem;
            color: white;
            padding: 0.5rem;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
        }
    </style>
    <!-- Script para cargar el color dinámico del ODS y la navegación -->
    <script>
        // Definición de los ODS y sus colores
        const sdgGoals = [
            { id: 1, title: "Fin de la Pobreza", color: "var(--color-1)", icon: "💰" },
            { id: 2, title: "Hambre Cero", color: "var(--color-2)", icon: "🍽️" },
            { id: 3, title: "Salud y Bienestar", color: "var(--color-3)", icon: "❤️" },
            { id: 4, title: "Educación de Calidad", color: "var(--color-4)", icon: "📚" },
            { id: 5, title: "Igualdad de Género", color: "var(--color-5)", icon: "♀️" },
            { id: 6, title: "Agua Limpia y Saneamiento", color: "var(--color-6)", icon: "💧" },
            { id: 7, title: "Energía Asequible y No Contaminante", color: "var(--color-7)", icon: "💡" },
            { id: 8, title: "Trabajo Decente y Crecimiento Económico", color: "var(--color-8)", icon: "💼" },
            { id: 9, title: "Industria, Innovación e Infraestructura", color: "var(--color-9)", icon: "🏗️" },
            { id: 10, title: "Reducción de las Desigualdades", color: "var(--color-10)", icon: "⚖️" },
            { id: 11, title: "Ciudades y Comunidades Sostenibles", color: "var(--color-11)", icon: "🏙️" },
            { id: 12, title: "Producción y Consumo Responsables", color: "var(--color-12)", icon: "♻️" },
            { id: 13, title: "Acción por el Clima", color: "var(--color-13)", icon: "🌎" },
            { id: 14, title: "Vida Submarina", color: "var(--color-14)", icon: "🐠" },
            { id: 15, title: "Vida de Ecosistemas Terrestres", color: "var(--color-15)", icon: "🌳" },
            { id: 16, title: "Paz, Justicia e Instituciones Sólidas", color: "var(--color-16)", icon: "🕊️" },
            { id: 17, title: "Alianzas para Lograr los Objetivos", color: "var(--color-17)", icon: "🤝" }
        ];

        // Función para renderizar dinámicamente las tarjetas de los ODS en la página de inicio
        function renderSDGCards() {
            const container = document.getElementById('ods-grid');
            if (!container) return;

            sdgGoals.forEach(goal => {
                const cardHtml = `
                    <a href="#ods-${goal.id}" class="ods-card bg-white p-6 rounded-xl shadow-lg flex flex-col items-center text-center cursor-pointer border-t-8 transition duration-300 hover:shadow-xl" 
                       style="border-top-color: ${goal.color};">
                        <div class="ods-goal-icon bg-gray-100 mb-4" style="background-color: ${goal.color};">
                            <span class="text-3xl">${goal.icon}</span>
                        </div>
                        <h3 class="text-xl font-bold mb-2 text-gray-800">ODS ${goal.id}: ${goal.title}</h3>
                        <p class="text-sm text-gray-600">Ver actividades para ${goal.title}.</p>
                    </a>
                `;
                container.innerHTML += cardHtml;
            });
        }

        // Función para renderizar dinámicamente las secciones de detalle de cada ODS
        function renderSDGSections() {
            const container = document.getElementById('ods-sections');
            if (!container) return;

            // Datos de descripción y actividades (Se usarán datos genéricos basados en la investigación)
            const activitiesData = {
                1: {
                    desc: "Poner fin a la pobreza en todas sus formas en todo el mundo.",
                    individual: ["Comprar productos de comercio justo para apoyar ingresos justos.", "Donar ropa y alimentos a bancos de alimentos locales.", "Aprender sobre programas de microfinanzas y apoyar a emprendedores.",],
                    school: ["Organizar una campaña de recaudación de fondos para una ONG local de lucha contra la pobreza.", "Integrar la educación financiera básica en el plan de estudios.", "Crear un banco de ropa escolar para estudiantes con necesidad.",],
                    business: ["Asegurar que todos los empleados reciban un salario digno, no solo el mínimo legal.", "Invertir en comunidades locales y contratar a personas de grupos vulnerables.", "Establecer una política de cero desechos para minimizar costos y redistribuir excedentes.",],
                },
                2: {
                    desc: "Poner fin al hambre, lograr la seguridad alimentaria y la mejora de la nutrición y promover la agricultura sostenible.",
                    individual: ["Reducir el desperdicio de alimentos planificando comidas y almacenando correctamente.", "Comprar frutas y verduras de temporada y de productores locales.", "Plantar un pequeño huerto o participar en un huerto comunitario.",],
                    school: ["Establecer un programa de almuerzo escolar que promueva comidas nutritivas y locales.", "Crear un 'Comité Hambre Cero' para monitorear el desperdicio de alimentos.", "Educar a los estudiantes sobre la importancia de la biodiversidad agrícola.",],
                    business: ["Implementar la trazabilidad de alimentos para reducir pérdidas en la cadena de suministro.", "Donar excedentes de alimentos que aún son seguros a organizaciones benéficas.", "Adoptar prácticas de agricultura regenerativa o apoyar a proveedores que lo hagan.",],
                },
                // Secciones genéricas para el resto de los ODS (ODS 3 a 17) para cumplir con el requisito de la estructura
                3: {
                    desc: "Garantizar una vida sana y promover el bienestar para todos en todas las edades.",
                    individual: ["Realizar actividad física regularmente.", "Promover la salud mental mediante la meditación o el descanso adecuado.", "Donar sangre periódicamente.",],
                    school: ["Promover programas de educación sexual integral y salud mental.", "Organizar días de deportes y actividades físicas.", "Asegurar un botiquín de primeros auxilios bien abastecido y personal capacitado.",],
                    business: ["Ofrecer seguro médico y programas de bienestar mental a los empleados.", "Crear un entorno de trabajo ergonómico y seguro.", "Invertir en investigación médica o donar a hospitales locales.",],
                },
                4: {
                    desc: "Garantizar una educación inclusiva, equitativa y de calidad y promover oportunidades de aprendizaje durante toda la vida para todos.",
                    individual: ["Ser mentor de un estudiante local.", "Donar libros a bibliotecas o escuelas.", "Participar en el aprendizaje continuo (cursos, talleres).",],
                    school: ["Ofrecer tutorías gratuitas y programas extracurriculares.", "Proporcionar acceso a tecnología y recursos digitales a todos los estudiantes.", "Capacitar a docentes en pedagogías inclusivas y de calidad.",],
                    business: ["Ofrecer pasantías y programas de formación para jóvenes.", "Asociarse con escuelas para programas STEM (ciencia, tecnología, ingeniería y matemáticas).", "Proporcionar licencias de estudio y formación continua a los empleados.",],
                },
                5: {
                    desc: "Lograr la igualdad entre los géneros y empoderar a todas las mujeres y las niñas.",
                    individual: ["Cuestionar los estereotipos de género en conversaciones y medios.", "Apoyar negocios propiedad de mujeres.", "Promover la distribución equitativa de las tareas domésticas.",],
                    school: ["Establecer clubes de liderazgo femenino y masculino.", "Revisar los materiales educativos para eliminar sesgos de género.", "Crear políticas de tolerancia cero para el acoso de género.",],
                    business: ["Garantizar la igualdad salarial por el mismo trabajo.", "Promover mujeres a puestos de liderazgo.", "Ofrecer licencias de paternidad y maternidad equitativas y flexibles.",],
                },
                6: {
                    desc: "Garantizar la disponibilidad de agua y su gestión sostenible y el saneamiento para todos.",
                    individual: ["Tomar duchas más cortas.", "Reutilizar el agua de lluvia para regar plantas.", "No arrojar medicamentos o productos químicos por el desagüe.",],
                    school: ["Instalar grifos y sanitarios de bajo consumo.", "Educar sobre el ciclo del agua y el saneamiento seguro.", "Monitorear y publicar el consumo de agua mensual.",],
                    business: ["Implementar tecnologías de reutilización y reciclaje de agua en las operaciones.", "Reducir la huella hídrica en la cadena de suministro.", "Invertir en infraestructura de saneamiento en comunidades cercanas.",],
                },
                7: {
                    desc: "Garantizar el acceso a una energía asequible, segura, sostenible y moderna para todos.",
                    individual: ["Cambiar a bombillas LED de bajo consumo.", "Desconectar los aparatos electrónicos cuando no se usen (cargas fantasma).", "Utilizar el transporte público o la bicicleta.",],
                    school: ["Instalar paneles solares en el techo de la escuela.", "Apagar luces y equipos en aulas vacías.", "Incluir la eficiencia energética en el plan de estudios.",],
                    business: ["Cambiar a fuentes de energía renovable 100%.", "Optimizar la eficiencia energética de los edificios y equipos.", "Ofrecer incentivos para el uso de vehículos eléctricos por parte de los empleados.",],
                },
                8: {
                    desc: "Promover el crecimiento económico sostenido, inclusivo y sostenible, el empleo pleno y productivo y el trabajo decente para todos.",
                    individual: ["Apoyar a pequeñas empresas y emprendedores locales.", "Denunciar cualquier forma de trabajo no ético o explotación.", "Desarrollar nuevas habilidades a través de la formación continua.",],
                    school: ["Organizar ferias de empleo y orientación vocacional.", "Promover el espíritu empresarial entre los estudiantes.", "Asegurar que los proveedores de la escuela cumplan con normas laborales justas.",],
                    business: ["Garantizar condiciones de trabajo seguras y saludables.", "Ofrecer oportunidades de ascenso y desarrollo profesional.", "Adoptar políticas de no discriminación y de inclusión laboral.",],
                },
                9: {
                    desc: "Construir infraestructuras resilientes, promover la industrialización inclusiva y sostenible y fomentar la innovación.",
                    individual: ["Apoyar a negocios que utilizan tecnología sostenible.", "Participar en encuestas cívicas sobre mejoras de infraestructura local.", "Promover el uso de transporte público y sostenible.",],
                    school: ["Invertir en infraestructura escolar resistente a desastres.", "Establecer laboratorios de innovación (makerspaces).", "Organizar concursos de diseño de soluciones para problemas de infraestructura local.",],
                    business: ["Invertir en investigación y desarrollo de tecnologías verdes.", "Utilizar materiales de construcción sostenibles y locales.", "Modernizar las instalaciones para aumentar la eficiencia y la resiliencia.",],
                },
                10: {
                    desc: "Reducir la desigualdad en y entre los países.",
                    individual: ["Ser un aliado activo en la lucha contra la discriminación.", "Apoyar a organizaciones que trabajan con poblaciones marginadas.", "Promover la inclusión de personas con discapacidad.",],
                    school: ["Garantizar que los programas y las actividades sean accesibles para todos.", "Organizar talleres sobre diversidad e inclusión.", "Establecer un sistema de becas para estudiantes de bajos recursos.",],
                    business: ["Implementar un plan de diversidad, equidad e inclusión (DEI).", "Evaluar los salarios para cerrar brechas de ingresos por raza, género, etc.", "Asegurar que las campañas de marketing sean inclusivas.",],
                },
                11: {
                    desc: "Lograr que las ciudades y los asentamientos humanos sean inclusivos, seguros, resilientes y sostenibles.",
                    individual: ["Utilizar el transporte público, caminar o andar en bicicleta.", "Participar en la limpieza de parques y espacios verdes.", "Apoyar la zonificación y el desarrollo de viviendas asequibles.",],
                    school: ["Crear un plan de respuesta a desastres y simulacros regulares.", "Promover el uso de la bicicleta y el transporte ecológico para ir a la escuela.", "Colaborar con el gobierno local en proyectos de mejora urbana.",],
                    business: ["Contribuir a la creación de espacios públicos verdes cerca de las oficinas.", "Utilizar materiales de construcción de bajo impacto ambiental.", "Diseñar productos y servicios accesibles para todos los habitantes.",],
                },
                12: {
                    desc: "Garantizar modalidades de consumo y producción sostenibles.",
                    individual: ["Seguir la regla de las 3 R: Reducir, Reutilizar, Reciclar.", "Comprar solo lo necesario y evitar el 'fast fashion'.", "Elegir productos con envases mínimos o reciclables.",],
                    school: ["Implementar un sistema de reciclaje integral (papel, plástico, orgánico).", "Impartir clases sobre consumo responsable y el impacto de los residuos.", "Usar papel reciclado y material de oficina sostenible.",],
                    business: ["Establecer objetivos de reducción de residuos de 'cero a vertedero'.", "Diseñar productos para que sean duraderos, reparables y reciclables (Economía Circular).", "Informar de manera transparente sobre el impacto ambiental de sus productos.",],
                },
                13: {
                    desc: "Adoptar medidas urgentes para combatir el cambio climático y sus efectos.",
                    individual: ["Reducir el consumo de carne y productos lácteos.", "Calcular y compensar tu huella de carbono.", "Presionar a los líderes políticos y empresariales para que tomen medidas climáticas.",],
                    school: ["Realizar auditorías energéticas y reducir las emisiones de carbono de la escuela.", "Organizar un 'Día de la Acción Climática' con actividades educativas.", "Integrar el cambio climático en todas las materias.",],
                    business: ["Establecer objetivos de reducción de gases de efecto invernadero basados en la ciencia.", "Invertir en tecnologías de captura de carbono o reforestación.", "Hacer que la resiliencia climática sea parte de la planificación empresarial.",],
                },
                14: {
                    desc: "Conservar y utilizar en forma sostenible los océanos, los mares y los recursos marinos para el desarrollo sostenible.",
                    individual: ["Participar en limpiezas de playas o ríos.", "Evitar los productos de plástico de un solo uso.", "Consumir pescado de forma sostenible (ver guías de consumo responsable).",],
                    school: ["Organizar una excursión a la costa para limpiar y educar.", "Crear arte con basura marina para concienciar.", "Estudiar la acidificación de los océanos en las clases de ciencias.",],
                    business: ["Reducir el uso de plástico en el embalaje y la cadena de suministro.", "Asegurar prácticas de pesca o abastecimiento de mariscos sostenibles (si aplica).", "Invertir en tecnologías para limpiar la contaminación marina.",],
                },
                15: {
                    desc: "Proteger, restablecer y promover el uso sostenible de los ecosistemas terrestres, gestionar los bosques de forma sostenible, luchar contra la desertificación, detener e invertir la degradación de las tierras y poner freno a la pérdida de la diversidad biológica.",
                    individual: ["Apoyar programas de reforestación local.", "Evitar el uso de pesticidas y herbicidas en tu jardín.", "Ser voluntario en un refugio de vida silvestre o parque nacional.",],
                    school: ["Crear un jardín de polinizadores o un 'bosque comestible'.", "Organizar caminatas educativas sobre la biodiversidad local.", "Enseñar sobre la importancia de la conservación de los suelos.",],
                    business: ["Utilizar papel certificado (FSC) y madera sostenible.", "Evitar el abastecimiento de productos que contribuyen a la deforestación.", "Restaurar tierras degradadas en propiedades de la empresa.",],
                },
                16: {
                    desc: "Promover sociedades pacíficas e inclusivas para el desarrollo sostenible, facilitar el acceso a la justicia para todos y crear instituciones eficaces, responsables e inclusivas a todos los niveles.",
                    individual: ["Votar en elecciones locales y nacionales.", "Informarse sobre las leyes locales y los derechos humanos.", "Ser un mediador en conflictos cotidianos.",],
                    school: ["Establecer un consejo estudiantil democrático y representativo.", "Implementar programas de resolución de conflictos y mediación entre compañeros.", "Enseñar sobre derechos humanos y el estado de derecho.",],
                    business: ["Adoptar códigos de ética y políticas anticorrupción rigurosas.", "Garantizar la transparencia en la presentación de informes y la toma de decisiones.", "Ofrecer servicios pro bono o apoyo legal a la comunidad.",],
                },
                17: {
                    desc: "Fortalecer los medios de ejecución y revitalizar la Alianza Mundial para el Desarrollo Sostenible.",
                    individual: ["Colaborar con organizaciones benéficas, tanto locales como internacionales.", "Compartir información fiable sobre los ODS en redes sociales.", "Participar en eventos de promoción de los ODS.",],
                    school: ["Asociarse con escuelas en otros países para proyectos de intercambio cultural y ODS.", "Buscar patrocinio de empresas para proyectos escolares de sostenibilidad.", "Participar en la Red de Escuelas Asociadas de la UNESCO.",],
                    business: ["Formar alianzas público-privadas para proyectos de infraestructura sostenible.", "Compartir tecnología y conocimientos (transferencia tecnológica) con países en desarrollo.", "Unirse a iniciativas globales como el Pacto Mundial de la ONU.",],
                }
            };

            sdgGoals.forEach(goal => {
                const data = activitiesData[goal.id];
                const sectionHtml = `
                    <section id="ods-${goal.id}" class="py-16 md:py-20 snap-start">
                        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                            <div class="p-8 rounded-xl shadow-2xl bg-white border-b-8" style="border-bottom-color: ${goal.color};">
                                <div class="flex items-center space-x-4 mb-8 border-b pb-4">
                                    <div class="ods-goal-icon" style="background-color: ${goal.color};">
                                        <span class="text-4xl font-extrabold">${goal.id}</span>
                                    </div>
                                    <h2 class="text-3xl sm:text-4xl font-extrabold text-gray-900">${goal.title}</h2>
                                </div>
                                
                                <!-- Descripción del Objetivo -->
                                <p class="text-xl text-gray-700 mb-8 italic">
                                    ${data.desc}
                                </p>

                                <!-- Contenedores de Actividades -->
                                <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                                    <!-- Actividades Individuales -->
                                    <div class="p-6 rounded-lg bg-red-50 border-l-4 border-red-500">
                                        <h3 class="text-2xl font-semibold mb-4 text-red-700 flex items-center">
                                            <span class="mr-2 text-3xl">👤</span> Actividades Individuales
                                        </h3>
                                        <ul class="space-y-3 text-gray-700 list-disc list-inside">
                                            ${data.individual.map(a => `<li>${a}</li>`).join('')}
                                        </ul>
                                    </div>

                                    <!-- Actividades Escolares -->
                                    <div class="p-6 rounded-lg bg-blue-50 border-l-4 border-blue-500">
                                        <h3 class="text-2xl font-semibold mb-4 text-blue-700 flex items-center">
                                            <span class="mr-2 text-3xl">🏫</span> Actividades Escolares
                                        </h3>
                                        <ul class="space-y-3 text-gray-700 list-disc list-inside">
                                            ${data.school.map(a => `<li>${a}</li>`).join('')}
                                        </ul>
                                    </div>

                                    <!-- Actividades Empresariales -->
                                    <div class="p-6 rounded-lg bg-green-50 border-l-4 border-green-500">
                                        <h3 class="text-2xl font-semibold mb-4 text-green-700 flex items-center">
                                            <span class="mr-2 text-3xl">🏢</span> Actividades Empresariales
                                        </h3>
                                        <ul class="space-y-3 text-gray-700 list-disc list-inside">
                                            ${data.business.map(a => `<li>${a}</li>`).join('')}
                                        </ul>
                                    </div>
                                </div>
                                
                                <!-- Placeholder de Imagen/Vídeo -->
                                <div class="mt-8 p-6 bg-gray-100 rounded-lg text-center border border-dashed border-gray-400">
                                    <p class="text-gray-600 font-medium">
                                        [Espacio para Imagen o Video que ilustre el ODS ${goal.id}]
                                    </p>
                                    <p class="text-sm text-gray-500 mt-2">
                                        Sugerencia: Una imagen de alta resolución o un gráfico que represente el objetivo o una de las actividades clave.
                                    </p>
                                </div>
                                <div class="text-center mt-8">
                                    <a href="#top" class="inline-flex items-center text-sm font-medium text-white bg-gray-800 hover:bg-gray-700 px-4 py-2 rounded-full transition duration-150">
                                        Volver a la cuadrícula de ODS
                                    </a>
                                </div>
                            </div>
                        </div>
                    </section>
                `;
                container.innerHTML += sectionHtml;
            });
        }

        // Se ejecuta al cargar la ventana
        window.onload = function() {
            renderSDGCards();
            renderSDGSections();
        };

        // Función para cambiar la visibilidad del menú móvil
        function toggleMobileMenu() {
            const menu = document.getElementById('mobile-menu');
            menu.classList.toggle('hidden');
        }
    </script>
</head>

<body class="antialiased text-gray-800">

    <!-- Navegación Principal -->
    <header id="top" class="ods-header shadow-lg sticky top-0 z-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center py-4 md:justify-start md:space-x-10">
                <div class="flex justify-start lg:w-0 lg:flex-1">
                    <a href="#top" class="flex items-center">
                        <span class="text-3xl font-extrabold text-white mr-2">ODS</span>
                        <span class="text-xl font-medium text-white hidden sm:inline">en Acción</span>
                    </a>
                </div>
                <!-- Menú de navegación principal (Escritorio) -->
                <nav class="hidden md:flex space-x-10">
                    <a href="#inicio" class="text-base font-medium text-white hover:text-gray-300 transition duration-150">
                        Inicio
                    </a>
                    <a href="#ods-sections" class="text-base font-medium text-white hover:text-gray-300 transition duration-150">
                        Los 17 ODS
                    </a>
                    <a href="#recursos" class="text-base font-medium text-white hover:text-gray-300 transition duration-150">
                        Recursos
                    </a>
                </nav>
                <!-- Botón de menú móvil -->
                <div class="-mr-2 -my-2 md:hidden">
                    <button type="button" onclick="toggleMobileMenu()" class="bg-white rounded-md p-2 inline-flex items-center justify-center text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500" aria-expanded="false">
                        <span class="sr-only">Abrir menú</span>
                        <!-- Icono de menú (Hamburguesa) -->
                        <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
                        </svg>
                    </button>
                </div>
            </div>
        </div>

        <!-- Menú móvil, toggle con JS -->
        <div id="mobile-menu" class="hidden absolute top-full inset-x-0 p-2 transition transform origin-top-right md:hidden">
            <div class="rounded-lg shadow-lg ring-1 ring-black ring-opacity-5 bg-white divide-y-2 divide-gray-50">
                <div class="pt-5 pb-6 px-5">
                    <div class="flex items-center justify-between">
                        <div class="flex items-center">
                            <span class="text-xl font-extrabold text-gray-800 mr-2">ODS</span>
                            <span class="text-lg font-medium text-gray-600">en Acción</span>
                        </div>
                        <div class="-mr-2">
                            <button type="button" onclick="toggleMobileMenu()" class="bg-white rounded-md p-2 inline-flex items-center justify-center text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500">
                                <span class="sr-only">Cerrar menú</span>
                                <!-- Icono de cierre (X) -->
                                <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                                </svg>
                            </button>
                        </div>
                    </div>
                    <div class="mt-6">
                        <nav class="grid gap-y-8">
                            <a href="#inicio" onclick="toggleMobileMenu()" class="-m-3 p-3 flex items-center rounded-md hover:bg-gray-50 transition duration-150">
                                <span class="text-base font-medium text-gray-900">Inicio</span>
                            </a>
                            <a href="#ods-sections" onclick="toggleMobileMenu()" class="-m-3 p-3 flex items-center rounded-md hover:bg-gray-50 transition duration-150">
                                <span class="text-base font-medium text-gray-900">Los 17 ODS</span>
                            </a>
                            <a href="#recursos" onclick="toggleMobileMenu()" class="-m-3 p-3 flex items-center rounded-md hover:bg-gray-50 transition duration-150">
                                <span class="text-base font-medium text-gray-900">Recursos</span>
                            </a>
                        </nav>
                    </div>
                </div>
            </div>
        </div>
    </header>

    <main>
        <!-- Sección de Inicio y Propósito (Página de Inicio) -->
        <section id="inicio" class="relative bg-white pt-12 sm:pt-16 lg:pt-20">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center">
                    <h1 class="text-4xl tracking-tight font-extrabold text-gray-900 sm:text-5xl md:text-6xl">
                        Los 17 <span class="ods-header p-1 rounded-lg text-white">Objetivos de Desarrollo Sostenible</span>
                    </h1>
                    <p class="mt-3 max-w-md mx-auto text-xl text-gray-500 sm:text-2xl md:mt-5 md:max-w-3xl">
                        Tu plataforma para inspirar y catalizar acciones en tu comunidad, escuela o empresa.
                    </p>
                </div>
                <div class="mt-10 mb-12">
                    <!-- Placeholder de Imagen/Infografía Atractiva -->
                    <img src="https://placehold.co/1200x400/19486a/ffffff?text=Infografía+de+los+17+ODS" 
                         alt="Infografía de los 17 Objetivos de Desarrollo Sostenible" 
                         class="w-full h-auto object-cover rounded-xl shadow-2xl border-4 border-white">
                </div>
            </div>
        </section>

        <!-- Sección de Cuadrícula de ODS (Estructura de Navegación) -->
        <section id="ods-overview" class="py-16 bg-gray-50">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <h2 class="text-3xl font-extrabold text-gray-900 mb-10 text-center">
                    Explora los Objetivos y Actividades
                </h2>
                <div id="ods-grid" class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-4 xl:grid-cols-5 gap-6">
                    <!-- Las tarjetas de los ODS se renderizarán aquí mediante JavaScript -->
                </div>
            </div>
        </section>
        
        <!-- Contenedor para las Secciones Detalladas de los 17 ODS -->
        <div id="ods-sections" class="scroll-smooth">
            <!-- Las secciones detalladas de cada ODS se renderizarán aquí mediante JavaScript -->
        </div>

        <!-- Sección de Recursos -->
        <section id="recursos" class="py-20 bg-white">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-12">
                    <h2 class="text-4xl font-extrabold text-gray-900">Recursos Clave para la Acción</h2>
                    <p class="mt-4 text-xl text-gray-600">
                        Profundiza tu conocimiento y encuentra más herramientas para implementar los ODS.
                    </p>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                    <!-- Recurso 1: Sitio Oficial de la ONU -->
                    <div class="p-6 bg-yellow-50 rounded-xl shadow-lg hover:shadow-xl transition duration-300">
                        <h3 class="text-2xl font-semibold text-gray-800 mb-3">Sitio Oficial ODS - ONU</h3>
                        <p class="text-gray-600 mb-4">
                            Información detallada, metas y avances globales de cada objetivo. Fuente principal de datos.
                        </p>
                        <a href="https://www.un.org/sustainabledevelopment/es/" target="_blank"
                           class="text-blue-600 hover:text-blue-800 font-medium flex items-center">
                            Visitar el sitio de la ONU 
                            <svg class="ml-1 w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4m-4-7l-4 4m0 0l4 4m4-11V3h-6"></path></svg>
                        </a>
                    </div>

                    <!-- Recurso 2: Herramientas para Empresas -->
                    <div class="p-6 bg-yellow-50 rounded-xl shadow-lg hover:shadow-xl transition duration-300">
                        <h3 class="text-2xl font-semibold text-gray-800 mb-3">Pacto Mundial de la ONU</h3>
                        <p class="text-gray-600 mb-4">
                            Guías y marcos para que las empresas alineen sus estrategias y operaciones con los ODS.
                        </p>
                        <a href="https://www.pactomundial.org/" target="_blank"
                           class="text-blue-600 hover:text-blue-800 font-medium flex items-center">
                            Recursos para Empresas
                            <svg class="ml-1 w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4m-4-7l-4 4m0 0l4 4m4-11V3h-6"></path></svg>
                        </a>
                    </div>

                    <!-- Recurso 3: Material Didáctico para Escuelas -->
                    <div class="p-6 bg-yellow-50 rounded-xl shadow-lg hover:shadow-xl transition duration-300">
                        <h3 class="text-2xl font-semibold text-gray-800 mb-3">Materiales Educativos ODS</h3>
                        <p class="text-gray-600 mb-4">
                            Juegos, guías y actividades didácticas para integrar los ODS en el currículo escolar.
                        </p>
                        <a href="https://es.unesco.org/themes/educacion-desarrollo-sostenible/ods" target="_blank"
                           class="text-blue-600 hover:text-blue-800 font-medium flex items-center">
                            Explorar Material Didáctico
                            <svg class="ml-1 w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4m-4-7l-4 4m0 0l4 4m4-11V3h-6"></path></svg>
                        </a>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Pie de Página -->
    <footer class="ods-header mt-12">
        <div class="max-w-7xl mx-auto py-8 px-4 overflow-hidden sm:px-6 lg:px-8 text-center">
            <p class="text-center text-base text-gray-300">
                &copy; 2024 ODS en Acción. Proyecto Educativo para la Agenda 2030.
            </p>
        </div>
    </footer>

</body>
</html>
