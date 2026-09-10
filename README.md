<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shree Kheteswar Energy Station - IOCL | NH125</title>
    
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;800&display=swap" rel="stylesheet">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        poppins: ['Poppins', 'sans-serif'],
                    },
                    colors: {
                        ioclOrange: '#F58220',
                        ioclBlue: '#0033A0',
                        sand: '#EDC9AF'
                    }
                }
            }
        }
    </script>
    <style>
        body, html {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100%;
            overflow-x: hidden;
            font-family: 'Poppins', sans-serif;
            background-color: #000;
        }

        #webgl-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            pointer-events: none; /* Let clicks pass through to UI if needed, though we track mouse */
        }

        #ui-layer {
            position: relative;
            z-index: 10;
            width: 100%;
            min-height: 100%;
            pointer-events: none; /* Container doesn't block */
        }
        
        .interactive-element {
            pointer-events: auto; /* Re-enable clicks on actual UI elements */
        }

        .glass-panel {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.5);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        .glass-panel-dark {
            background: rgba(0, 15, 40, 0.8);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            color: white;
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar { width: 8px; }
        ::-webkit-scrollbar-track { background: transparent; }
        ::-webkit-scrollbar-thumb { background: #F58220; border-radius: 4px; }
        
        /* Entrance Animations */
        @keyframes fadeUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .animate-fade-up { animation: fadeUp 1s ease-out forwards; }
        .delay-100 { animation-delay: 0.1s; }
        .delay-200 { animation-delay: 0.2s; }
        .delay-300 { animation-delay: 0.3s; }
    </style>
</head>
<body class="antialiased">

    <div id="webgl-container"></div>

    <div id="ui-layer" class="flex flex-col min-h-screen">
        
        <!-- Header -->
        <header class="interactive-element w-full p-4 md:p-6 flex justify-between items-center glass-panel sticky top-0 z-50">
            <div class="flex items-center gap-3">
                <!-- Simple IOCL Logo representation -->
                <div class="w-10 h-10 md:w-12 md:h-12 rounded-full border-4 border-ioclOrange flex items-center justify-center bg-ioclBlue">
                    <span class="text-white font-bold text-xs md:text-sm">IOCL</span>
                </div>
                <div>
                    <h1 class="text-lg md:text-2xl font-bold text-ioclBlue leading-tight">Shree Kheteswar</h1>
                    <p class="text-xs md:text-sm text-gray-600 font-semibold">Energy Station</p>
                </div>
            </div>
            <div class="hidden md:flex gap-4">
                <a href="tel:9414562003" class="text-ioclBlue font-bold hover:text-ioclOrange transition">📞 9414562003</a>
                <a href="tel:7877400426" class="text-ioclBlue font-bold hover:text-ioclOrange transition">📞 7877400426</a>
            </div>
        </header>

        <main class="flex-grow flex flex-col items-center justify-center p-4 text-center mt-20 md:mt-0">
            <div class="interactive-element max-w-4xl mx-auto p-8 rounded-3xl glass-panel-dark animate-fade-up">
                <div class="inline-block px-4 py-1 rounded-full bg-ioclOrange text-white font-bold text-xs md:text-sm mb-4 uppercase tracking-wider">
                    IndianOil - The Energy of India
                </div>
                <h2 class="text-4xl md:text-6xl font-extrabold mb-4 leading-tight">
                    Fueling Your Journey on the <span class="text-ioclOrange">Golden Sands</span>
                </h2>
                <p class="text-lg md:text-xl text-gray-300 mb-8 max-w-2xl mx-auto">
                    Your premium and trusted pitstop on the Jodhpur - Jaisalmer Highway (NH125). Experience top-quality fuels, essential services, and a refreshing break for your vehicle.
                </p>
                
                <div class="flex flex-col sm:flex-row gap-4 justify-center items-center">
                    <a href="https://maps.app.goo.gl/PixQQSjFd3KofvQv5?g_st=ic" target="_blank" class="interactive-element bg-ioclOrange hover:bg-orange-600 text-white font-bold py-4 px-8 rounded-full shadow-lg shadow-orange-500/50 transform transition hover:scale-105 flex items-center gap-2 text-lg w-full sm:w-auto justify-center">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z" />
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
                        </svg>
                        Navigate to Pump
                    </a>
                </div>
            </div>

            <div class="interactive-element w-full max-w-6xl mx-auto grid grid-cols-2 md:grid-cols-4 gap-4 mt-16 px-4 animate-fade-up delay-100">
                <!-- Petrol -->
                <div class="glass-panel p-6 rounded-2xl text-center transform transition hover:-translate-y-2">
                    <div class="w-16 h-16 mx-auto bg-green-100 rounded-full flex items-center justify-center mb-4 text-3xl">⛽</div>
                    <h3 class="font-bold text-gray-800 text-lg">Regular Petrol</h3>
                    <p class="text-sm text-gray-500 mt-2">100% Pure & Assured Quantity</p>
                </div>
                <!-- HSD -->
                <div class="glass-panel p-6 rounded-2xl text-center transform transition hover:-translate-y-2">
                    <div class="w-16 h-16 mx-auto bg-blue-100 rounded-full flex items-center justify-center mb-4 text-3xl">🛢️</div>
                    <h3 class="font-bold text-gray-800 text-lg">HSD (Diesel)</h3>
                    <p class="text-sm text-gray-500 mt-2">High-Speed Diesel for heavy duty</p>
                </div>
                <!-- Engine Oil -->
                <div class="glass-panel p-6 rounded-2xl text-center transform transition hover:-translate-y-2">
                    <div class="w-16 h-16 mx-auto bg-yellow-100 rounded-full flex items-center justify-center mb-4 text-3xl">💧</div>
                    <h3 class="font-bold text-gray-800 text-lg">Engine Oils</h3>
                    <p class="text-sm text-gray-500 mt-2">Premium Servo Oils available</p>
                </div>
                <!-- Equipment -->
                <div class="glass-panel p-6 rounded-2xl text-center transform transition hover:-translate-y-2">
                    <div class="w-16 h-16 mx-auto bg-gray-100 rounded-full flex items-center justify-center mb-4 text-3xl">🛠️</div>
                    <h3 class="font-bold text-gray-800 text-lg">Other Equipment</h3>
                    <p class="text-sm text-gray-500 mt-2">Essential vehicular accessories</p>
                </div>
            </div>
        </main>

        <footer class="w-full mt-16 p-4 md:p-8">
            <div class="interactive-element max-w-4xl mx-auto glass-panel rounded-3xl p-6 md:p-10 animate-fade-up delay-200">
                <div class="grid grid-cols-1 md:grid-cols-2 gap-8 text-center md:text-left">
                    <div>
                        <h4 class="text-2xl font-bold text-ioclBlue mb-2">Management</h4>
                        <div class="mt-4 space-y-3">
                            <p class="text-gray-700"><span class="font-bold text-gray-900">Owner:</span> Dr. As Rajpurohit</p>
                            <p class="text-gray-700"><span class="font-bold text-gray-900">Managing Director:</span> Suryadev Singh Rajpurohit</p>
                        </div>
                    </div>
                    <div class="flex flex-col justify-center items-center md:items-end">
                        <h4 class="text-lg font-bold text-gray-800 mb-4">24/7 Support & Inquiries</h4>
                        <a href="tel:9414562003" class="w-full md:w-auto bg-gray-900 hover:bg-gray-800 text-white py-3 px-6 rounded-xl font-bold mb-3 transition text-center shadow-md">
                            Call: +91 9414562003
                        </a>
                        <a href="tel:7877400426" class="w-full md:w-auto bg-gray-900 hover:bg-gray-800 text-white py-3 px-6 rounded-xl font-bold transition text-center shadow-md">
                            Call: +91 7877400426
                        </a>
                    </div>
                </div>
                <div class="mt-8 pt-6 border-t border-gray-200 text-center text-sm text-gray-500">
                    &copy; <span id="year"></span> Shree Kheteswar Energy Station. NH125 Jodhpur - Jaisalmer Highway. All rights reserved.
                </div>
            </div>
        </footer>
    </div>

    <script>
        document.getElementById('year').innerText = new Date().getFullYear();

        // 1. Scene Setup
        const container = document.getElementById('webgl-container');
        const scene = new THREE.Scene();
        
        // Desert Sunset Theme
        scene.background = new THREE.Color(0xFFA07A); // Light Salmon / Warm Sunset
        scene.fog = new THREE.FogExp2(0xFFA07A, 0.008); // Blends the horizon

        const camera = new THREE.PerspectiveCamera(60, window.innerWidth / window.innerHeight, 0.1, 1000);
        // Position camera to look at the station from a slightly elevated dynamic angle
        camera.position.set(-15, 12, 35);
        
        const renderer = new THREE.WebGLRenderer({ antialias: true, alpha: false });
        renderer.setSize(window.innerWidth, window.innerHeight);
        renderer.setPixelRatio(window.devicePixelRatio);
        renderer.shadowMap.enabled = true;
        renderer.shadowMap.type = THREE.PCFSoftShadowMap;
        container.appendChild(renderer.domElement);

        const ambientLight = new THREE.AmbientLight(0xffeedd, 0.6); // Warm ambient
        scene.add(ambientLight);

        const dirLight = new THREE.DirectionalLight(0xffffff, 1.2);
        dirLight.position.set(-50, 50, -30); // Setting sun direction
        dirLight.castShadow = true;
        dirLight.shadow.mapSize.width = 2048;
        dirLight.shadow.mapSize.height = 2048;
        dirLight.shadow.camera.near = 0.5;
        dirLight.shadow.camera.far = 150;
        dirLight.shadow.camera.left = -50;
        dirLight.shadow.camera.right = 50;
        dirLight.shadow.camera.top = 50;
        dirLight.shadow.camera.bottom = -50;
        scene.add(dirLight);

        // Sand/Desert Floor
        const planeGeo = new THREE.PlaneGeometry(500, 500);
        const planeMat = new THREE.MeshStandardMaterial({ 
            color: 0xE1C699, // Desert sand
            roughness: 0.9,
            metalness: 0.1
        });
        const plane = new THREE.Mesh(planeGeo, planeMat);
        plane.rotation.x = -Math.PI / 2;
        plane.receiveShadow = true;
        scene.add(plane);

        // Highway (NH125)
        const roadGeo = new THREE.PlaneGeometry(16, 500);
        const roadMat = new THREE.MeshStandardMaterial({ color: 0x222222, roughness: 0.8 });
        const road = new THREE.Mesh(roadGeo, roadMat);
        road.rotation.x = -Math.PI / 2;
        road.position.set(20, 0.1, 0); // Offset road to the right
        road.receiveShadow = true;
        scene.add(road);

        // Highway Dashed Line
        const lineGeo = new THREE.PlaneGeometry(0.5, 500);
        const lineMat = new THREE.MeshBasicMaterial({ color: 0xffffff });
        // Use a simple trick for dashed lines with texture if available, or just solid for performance
        // We'll create multiple small planes for dashed effect
        const dashGroup = new THREE.Group();
        for(let i = -200; i < 200; i += 6) {
            const dash = new THREE.Mesh(new THREE.PlaneGeometry(0.4, 3), lineMat);
            dash.rotation.x = -Math.PI / 2;
            dash.position.set(20, 0.15, i);
            dashGroup.add(dash);
        }
        scene.add(dashGroup);

        const stationGroup = new THREE.Group();
        scene.add(stationGroup);

        // Pump Base / Platform
        const platformGeo = new THREE.BoxGeometry(30, 0.5, 20);
        const platformMat = new THREE.MeshStandardMaterial({ color: 0xaaaaaa, roughness: 0.7 });
        const platform = new THREE.Mesh(platformGeo, platformMat);
        platform.position.set(0, 0.25, 0);
        platform.receiveShadow = true;
        stationGroup.add(platform);

        // Canopy (IOCL Colors: Orange & Blue)
        const canopyGeo = new THREE.BoxGeometry(28, 2, 18);
        const canopyMat = new THREE.MeshStandardMaterial({ color: 0xffffff, roughness: 0.5 });
        const canopy = new THREE.Mesh(canopyGeo, canopyMat);
        canopy.position.set(0, 10, 0);
        canopy.castShadow = true;
        canopy.receiveShadow = true;
        
        // Add color stripes to canopy (Orange bottom, Blue top rim)
        const stripeOrangeGeo = new THREE.BoxGeometry(28.2, 0.6, 18.2);
        const stripeOrangeMat = new THREE.MeshStandardMaterial({ color: 0xF58220 });
        const stripeOrange = new THREE.Mesh(stripeOrangeGeo, stripeOrangeMat);
        stripeOrange.position.set(0, 9.5, 0);
        stationGroup.add(stripeOrange);

        const stripeBlueGeo = new THREE.BoxGeometry(28.2, 0.4, 18.2);
        const stripeBlueMat = new THREE.MeshStandardMaterial({ color: 0x0033A0 });
        const stripeBlue = new THREE.Mesh(stripeBlueGeo, stripeBlueMat);
        stripeBlue.position.set(0, 10.8, 0);
        stationGroup.add(stripeBlue);

        stationGroup.add(canopy);

        // Pillars
        const pillarGeo = new THREE.CylinderGeometry(0.5, 0.5, 9.5, 16);
        const pillarMat = new THREE.MeshStandardMaterial({ color: 0xcccccc, metalness: 0.8, roughness: 0.2 });
        const pillarPositions = [
            [-12, 5, -7], [12, 5, -7],
            [-12, 5, 7], [12, 5, 7]
        ];
        pillarPositions.forEach(pos => {
            const pillar = new THREE.Mesh(pillarGeo, pillarMat);
            pillar.position.set(...pos);
            pillar.castShadow = true;
            stationGroup.add(pillar);
        });

        // Dispensing Units (Machines)
        const machineGeo = new THREE.BoxGeometry(2, 3, 1.5);
        const machineMat = new THREE.MeshStandardMaterial({ color: 0xF58220 }); // Orange machines
        const machineWhiteMat = new THREE.MeshStandardMaterial({ color: 0xffffff });
        
        const mPos = [[-5, 1.5, 0], [5, 1.5, 0]];
        mPos.forEach(pos => {
            const mGroup = new THREE.Group();
            
            const base = new THREE.Mesh(machineGeo, machineMat);
            base.castShadow = true;
            
            const panel = new THREE.Mesh(new THREE.BoxGeometry(1.8, 1.5, 1.6), machineWhiteMat);
            panel.position.y = 0.5;
            
            mGroup.add(base);
            mGroup.add(panel);
            mGroup.position.set(...pos);
            stationGroup.add(mGroup);
        });

        // IOCL Signboard / Pylon
        const pylonGroup = new THREE.Group();
        const pylonPole = new THREE.Mesh(new THREE.CylinderGeometry(0.8, 0.8, 15), pillarMat);
        pylonPole.position.set(-15, 7.5, -15);
        
        const pylonSign = new THREE.Mesh(new THREE.BoxGeometry(6, 8, 2), new THREE.MeshStandardMaterial({ color: 0x0033A0 }));
        pylonSign.position.set(-15, 12, -15);
        
        const pylonLogo = new THREE.Mesh(new THREE.CircleGeometry(2, 32), new THREE.MeshStandardMaterial({ color: 0xF58220 }));
        pylonLogo.position.set(-15, 13, -13.9);
        
        pylonGroup.add(pylonPole, pylonSign, pylonLogo);
        scene.add(pylonGroup);

        function createSUV() {
            const car = new THREE.Group();
            const bodyMat = new THREE.MeshStandardMaterial({ 
                color: 0xffffff, 
                roughness: 0.2, 
                metalness: 0.1,
                clearcoat: 1.0 // Shiny white paint
            });
            const blackMat = new THREE.MeshStandardMaterial({ color: 0x111111, roughness: 0.9 });
            const glassMat = new THREE.MeshStandardMaterial({ color: 0x050505, roughness: 0.1, metalness: 0.8 });
            
            // Lower Body (Chassis) - Bulky
            const lowerBody = new THREE.Mesh(new THREE.BoxGeometry(2.4, 1.1, 5.5), bodyMat);
            lowerBody.position.y = 1.0;
            lowerBody.castShadow = true;
            car.add(lowerBody);

            // Upper Body (Cabin)
            const cabinGeo = new THREE.BoxGeometry(2.2, 0.9, 3.5);
            const cabin = new THREE.Mesh(cabinGeo, bodyMat);
            cabin.position.set(0, 2.0, -0.4);
            cabin.castShadow = true;
            car.add(cabin);

            // Windows (Windshield, Side, Rear)
            const windshield = new THREE.Mesh(new THREE.BoxGeometry(2.0, 0.7, 0.1), glassMat);
            windshield.position.set(0, 2.0, 1.35);
            windshield.rotation.x = -0.2;
            car.add(windshield);

            const rearGlass = new THREE.Mesh(new THREE.BoxGeometry(2.0, 0.6, 0.1), glassMat);
            rearGlass.position.set(0, 2.0, -2.15);
            car.add(rearGlass);
            
            const sideGlass1 = new THREE.Mesh(new THREE.BoxGeometry(0.1, 0.7, 2.8), glassMat);
            sideGlass1.position.set(1.11, 2.0, -0.4);
            car.add(sideGlass1);
            
            const sideGlass2 = new THREE.Mesh(new THREE.BoxGeometry(0.1, 0.7, 2.8), glassMat);
            sideGlass2.position.set(-1.11, 2.0, -0.4);
            car.add(sideGlass2);

            // Grille & Headlights
            const grille = new THREE.Mesh(new THREE.BoxGeometry(1.8, 0.6, 0.1), blackMat);
            grille.position.set(0, 1.1, 2.76);
            car.add(grille);

            const hlLightMat = new THREE.MeshStandardMaterial({ color: 0xffffff, emissive: 0xffffee, emissiveIntensity: 2 });
            const headlight1 = new THREE.Mesh(new THREE.BoxGeometry(0.4, 0.3, 0.1), hlLightMat);
            headlight1.position.set(0.9, 1.1, 2.76);
            car.add(headlight1);
            
            const headlight2 = new THREE.Mesh(new THREE.BoxGeometry(0.4, 0.3, 0.1), hlLightMat);
            headlight2.position.set(-0.9, 1.1, 2.76);
            car.add(headlight2);

            // Taillights
            const tlLightMat = new THREE.MeshStandardMaterial({ color: 0xff0000, emissive: 0xff0000, emissiveIntensity: 1 });
            const tailLight1 = new THREE.Mesh(new THREE.BoxGeometry(0.4, 0.3, 0.1), tlLightMat);
            tailLight1.position.set(0.9, 1.1, -2.76);
            car.add(tailLight1);
            
            const tailLight2 = new THREE.Mesh(new THREE.BoxGeometry(0.4, 0.3, 0.1), tlLightMat);
            tailLight2.position.set(-0.9, 1.1, -2.76);
            car.add(tailLight2);

            // Wheels (Big SUV Tires)
            const wheelGeo = new THREE.CylinderGeometry(0.5, 0.5, 0.4, 24);
            wheelGeo.rotateZ(Math.PI / 2);
            
            const wPositions = [
                [1.2, 0.5, 1.8], [-1.2, 0.5, 1.8],
                [1.2, 0.5, -1.8], [-1.2, 0.5, -1.8]
            ];
            
            car.wheels = []; // Store to rotate them during animation
            wPositions.forEach(pos => {
                const wheel = new THREE.Mesh(wheelGeo, blackMat);
                wheel.position.set(...pos);
                wheel.castShadow = true;
                
                // Rims
                const rim = new THREE.Mesh(new THREE.CylinderGeometry(0.3, 0.3, 0.42, 12), new THREE.MeshStandardMaterial({color: 0xcccccc, metalness: 0.8}));
                rim.rotateZ(Math.PI / 2);
                wheel.add(rim);

                car.add(wheel);
                car.wheels.push(wheel);
            });

            return car;
        }

        const suv = createSUV();
        scene.add(suv);

        // Add a point light to the front of the car simulating headlights illuminating the road
        const carHeadlightSpot = new THREE.SpotLight(0xffffff, 2, 50, Math.PI/6, 0.5, 1);
        carHeadlightSpot.position.set(0, 1, 3);
        carHeadlightSpot.target.position.set(0, 0, 10);
        suv.add(carHeadlightSpot);
        suv.add(carHeadlightSpot.target);

        // Initial Position (Far down the highway)
        suv.position.set(22, 0, -150);
        // Face forward along Z axis
        suv.rotation.y = 0;

        let animationState = 'driving_straight';
        const clock = new THREE.Clock();

        function updateCarAnimation(delta) {
            const speed = 25 * delta;
            const wheelSpeed = 10 * delta;
            
            // Rotate wheels
            suv.wheels.forEach(w => w.rotation.x += wheelSpeed);

            if (animationState === 'driving_straight') {
                suv.position.z += speed;
                
                // When car reaches z = 0, start turning into the pump
                if (suv.position.z >= 0) {
                    animationState = 'turning_left';
                }
            } 
            else if (animationState === 'turning_left') {
                // Smooth turn logic (circular arc)
                suv.rotation.y += 1.2 * delta; // Turn left
                suv.position.x -= speed * 0.8;
                suv.position.z += speed * 0.5;

                // Stop turning when faced roughly 90 degrees left (-Math.PI/2)
                if (suv.rotation.y >= Math.PI/2) {
                    suv.rotation.y = Math.PI/2;
                    animationState = 'driving_in';
                }
            }
            else if (animationState === 'driving_in') {
                suv.position.x -= speed * 0.8;
                
                // Stop at the dispensing machine
                if (suv.position.x <= 5) {
                    animationState = 'parked';
                }
            }
            else if (animationState === 'parked') {
                // Stop wheels
                suv.wheels.forEach(w => w.rotation.x = 0);
            }
        }

        let mouseX = 0;
        let mouseY = 0;
        let targetX = 0;
        let targetY = 0;

        const windowHalfX = window.innerWidth / 2;
        const windowHalfY = window.innerHeight / 2;

        document.addEventListener('mousemove', (event) => {
            mouseX = (event.clientX - windowHalfX);
            mouseY = (event.clientY - windowHalfY);
        });

        function animate() {
            requestAnimationFrame(animate);
            const delta = clock.getDelta();

            // Update Car
            updateCarAnimation(delta);

            // Camera Parallax
            targetX = mouseX * 0.005;
            targetY = mouseY * 0.005;
            
            camera.position.x += ((-15 + targetX) - camera.position.x) * 0.05;
            camera.position.y += ((12 - targetY) - camera.position.y) * 0.05;
            
            // Always look at the petrol pump station
            camera.lookAt(stationGroup.position);

            renderer.render(scene, camera);
        }

        window.addEventListener('resize', () => {
            camera.aspect = window.innerWidth / window.innerHeight;
            camera.updateProjectionMatrix();
            renderer.setSize(window.innerWidth, window.innerHeight);
        });

        // Start Animation Loop once everything is loaded
        window.onload = () => {
            animate();
        };

    </script>
</body>
</html>