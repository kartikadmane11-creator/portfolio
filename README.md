# portfolio
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kartik Admane - Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #2c3e50;
            background: #f8f9fa;
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid #e9ecef;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 1000;
            transition: all 0.3s ease;
            box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: #2c3e50;
            text-decoration: none;
            letter-spacing: -0.5px;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: #495057;
            text-decoration: none;
            transition: all 0.3s ease;
            padding: 0.5rem 1rem;
            border-radius: 6px;
            font-weight: 500;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -2px;
            left: 50%;
            width: 0;
            height: 2px;
            background: #3498db;
            transition: all 0.3s ease;
            transform: translateX(-50%);
        }

        .nav-links a:hover {
            color: #3498db;
            background: rgba(52, 152, 219, 0.1);
        }

        .nav-links a:hover::after {
            width: 80%;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding-top: 80px;
            position: relative;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(44, 62, 80, 0.8);
            z-index: 1;
        }

        .hero-content {
            position: relative;
            z-index: 2;
        }

        .hero-content h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            animation: fadeInUp 1s ease;
            font-weight: 700;
            letter-spacing: -1px;
        }

        .hero-content p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            animation: fadeInUp 1s ease 0.2s both;
            opacity: 0.9;
        }

        .btn {
            display: inline-block;
            padding: 14px 32px;
            background: #3498db;
            color: white;
            text-decoration: none;
            border-radius: 6px;
            transition: all 0.3s ease;
            border: none;
            animation: fadeInUp 1s ease 0.4s both;
            font-weight: 600;
            font-size: 1rem;
            cursor: pointer;
        }

        .btn:hover {
            background: #2980b9;
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(52, 152, 219, 0.3);
        }

        /* Sections */
        .section {
            padding: 80px 0;
            background: white;
            margin: 0;
            border-bottom: 1px solid #e9ecef;
        }

        .section:nth-child(even) {
            background: #f8f9fa;
        }

        .section h2 {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: #2c3e50;
            font-weight: 700;
            position: relative;
        }

        .section h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            width: 60px;
            height: 3px;
            background: #3498db;
            transform: translateX(-50%);
        }

        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 4rem;
            align-items: center;
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
            color: #495057;
        }

        .about-text p {
            margin-bottom: 1.5rem;
        }

        .about-image {
            text-align: center;
        }

        .profile-img {
            width: 280px;
            height: 280px;
            border-radius: 50%;
            background: linear-gradient(135deg, #2c3e50, #3498db);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 4rem;
            font-weight: 700;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        .profile-img:hover {
            transform: scale(1.05);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
        }

        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .skill-card {
            background: white;
            padding: 2rem;
            border-radius: 10px;
            text-align: center;
            transition: all 0.3s ease;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            border: 1px solid #e9ecef;
            position: relative;
            overflow: hidden;
            cursor: pointer;
        }

        .skill-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: #3498db;
            transform: translateX(-100%);
            transition: all 0.3s ease;
        }

        .skill-card:hover::before {
            transform: translateX(0);
        }

        .skill-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);
        }

        .skill-card h3 {
            font-size: 1.4rem;
            margin-bottom: 1rem;
            color: #2c3e50;
            font-weight: 600;
        }

        .skill-card p {
            color: #6c757d;
            line-height: 1.6;
        }

        .skill-card .click-hint {
            position: absolute;
            top: 10px;
            right: 10px;
            background: #3498db;
            color: white;
            padding: 4px 8px;
            border-radius: 12px;
            font-size: 0.8rem;
            opacity: 0;
            transition: all 0.3s ease;
        }

        .skill-card:hover .click-hint {
            opacity: 1;
        }

        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            z-index: 2000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0,0,0,0.8);
            backdrop-filter: blur(5px);
        }

        .modal-content {
            background-color: #fefefe;
            margin: 2% auto;
            padding: 0;
            width: 90%;
            max-width: 900px;
            border-radius: 15px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            position: relative;
            max-height: 90vh;
            overflow-y: auto;
        }

        .modal-header {
            background: linear-gradient(135deg, #3498db, #2980b9);
            color: white;
            padding: 2rem;
            border-radius: 15px 15px 0 0;
            position: relative;
        }

        .modal-header h2 {
            margin: 0;
            font-size: 2rem;
        }

        .close {
            color: white;
            position: absolute;
            top: 20px;
            right: 25px;
            font-size: 35px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .close:hover,
        .close:focus {
            transform: scale(1.1);
            text-shadow: 0 0 10px rgba(255,255,255,0.5);
        }

        .modal-body {
            padding: 2rem;
        }

        .documentation-section {
            margin-bottom: 2rem;
        }

        .documentation-section h3 {
            color: #2c3e50;
            margin-bottom: 1rem;
            font-size: 1.3rem;
            border-bottom: 2px solid #3498db;
            padding-bottom: 0.5rem;
        }

        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-top: 1rem;
        }

        .tech-tag {
            background: #3498db;
            color: white;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.9rem;
            font-weight: 500;
        }

        .screenshot-gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1rem;
            margin-top: 1rem;
        }

        .screenshot {
            background: #f8f9fa;
            border: 2px dashed #dee2e6;
            border-radius: 8px;
            height: 150px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #6c757d;
            font-style: italic;
            transition: all 0.3s ease;
            overflow: hidden; /* Ensure image doesn't overflow */
        }

        .screenshot img {
            max-width: 100%;
            max-height: 100%;
            object-fit: contain; /* Ensures the image fits within its container without cropping */
            border-radius: 5px;
        }

        .screenshot:hover {
            border-color: #3498db;
            background: rgba(52, 152, 219, 0.05);
        }

        .learning-points {
            list-style: none;
            padding: 0;
        }

        .learning-points li {
            background: #f8f9fa;
            margin: 0.5rem 0;
            padding: 1rem;
            border-left: 4px solid #3498db;
            border-radius: 0 8px 8px 0;
        }

        .learning-points li::before {
            content: '💡';
            margin-right: 10px;
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero-content h1 {
                font-size: 2.5rem;
            }

            .about-content {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .skills-grid {
                grid-template-columns: 1fr;
            }

            .modal-content {
                width: 95%;
                margin: 5% auto;
            }

            .modal-body {
                padding: 1rem;
            }
        }

        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.6s ease, transform 0.6s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <header>
        <nav class="container">
            <a href="#" class="logo">Kartik Admane</a>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#experience">Experience</a></li>
                <li><a href="#education">Education</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Kartik Admane</h1>
            <p>Dynamic Python Developer | Web Developer | 3D Designer</p>
            <a href="#contact" class="btn">Get In Touch</a>
        </div>
    </section>

    <div class="container">
        <section id="about" class="section fade-in">
            <h2>About Me</h2>
            <div class="about-content">
                <div class="about-image">
                    <div class="profile-img">KA</div>
                </div>
                <div class="about-text">
                    <p>I'm a dynamic Python developer with expertise in web development and 3D design. Currently pursuing Bachelor of Engineering in Information Technology from Shri Sant Gajanan Maharaj College of Engineering, Shegaon.</p>
                    <p>I have proven ability to create responsive web applications and optimize performance, while fostering collaboration and innovation. I'm skilled in iOS app development and committed to continuous professional growth.</p>
                    <p>I am currently seeking roles where I can utilize my experience and skills to contribute to innovative projects and grow professionally.</p>
                    <a href="Kartik_Admane_Resume.pdf" class="btn" style="margin-top: 1rem;" download>Download Resume</a>
                </div>
            </div>
        </section>

        <section id="skills" class="section fade-in">
            <h2>My Skills</h2>
            <div class="skills-grid">
                <div class="skill-card" onclick="openModal('python')">
                    <div class="click-hint">Click to explore</div>
                    <h3>Python Development</h3>
                    <p>Expert Python development with focus on web frameworks and automation libraries</p>
                </div>
                <div class="skill-card" onclick="openModal('web')">
                    <div class="click-hint">Click to explore</div>
                    <h3>Web Development</h3>
                    <p>Full-stack web development with HTML, CSS, JavaScript, jQuery, AJAX, and JSON for creating responsive websites</p>
                </div>
                <div class="skill-card" onclick="openModal('cyber')">
                    <div class="click-hint">Click to explore</div>
                    <h3>Cyber Security</h3>
                    <p>Security assessment, threat analysis, and implementing security measures in applications and systems</p>
                </div>
                <div class="skill-card" onclick="openModal('mobile')">
                    <div class="click-hint">Click to explore</div>
                    <h3>Mobile App Development</h3>
                    <p>iOS application development and native app development expertise</p>
                </div>
                <div class="skill-card" onclick="openModal('3d')">
                    <div class="click-hint">Click to explore</div>
                    <h3>3D Design & CAD</h3>
                    <p>Advanced 3D modeling and design using Fusion 360 for mechanical design and prototyping</p>
                </div>
                <div class="skill-card" onclick="openModal('pcb')">
                    <div class="click-hint">Click to explore</div>
                    <h3>PCB Design</h3>
                    <p>Electronic circuit design and PCB layout using KiCad for hardware development projects</p>
                </div>
                <div class="skill-card" onclick="openModal('3dprint')">
                    <div class="click-hint">Click to explore</div>
                    <img src="https://github.com/kartikadmane11-creator/portfolio/blob/main/WhatsApp%20Image%202025-09-24%20at%2012.12.54%20AM.jpeg" alt="WhatsApp Image 2025-09-24 at 12.12.54 AM.jpeg" width="500" height="600">

                    <h3>3D Printing</h3>
                    <p>3D printing technology, prototyping, and additive manufacturing for rapid product development</p>
                </div>
                <div class="skill-card" onclick="openModal('laser')">
                    <div class="click-hint">Click to explore</div>
                    <h3>Laser Cutting</h3>
                    <p>Precision laser cutting for prototyping, custom parts fabrication, and material processing</p>
                </div>
                <div class="skill-card" onclick="openModal('database')">
                    <div class="click-hint">Click to explore</div>
                    <h3>Database & Tools</h3>
                    <p>SQL, Git, GitHub for version control and database management</p>
                </div>
                <div class="skill-card" onclick="openModal('languages')">
                    <div class="click-hint">Click to explore</div>
                    <h3>Languages</h3>
                    <p>English, Hindi, Marathi</p>
                </div>
            </div>
        </section>

        <section id="projects" class="section fade-in">
            <h2>My Projects</h2>
            <div class="skills-grid">
                <div class="skill-card">
                    <h3>College Cultural Fest Management</h3>
                    <p>Planned and executed a college cultural fest with 1,000+ attendees, managing logistics, sponsorships, and promotions.</p>
                </div>
                <div class="skill-card">
                    <h3>Personal Portfolio Website</h3>
                    <p>Designed and developed a responsive personal portfolio website using HTML, CSS, and JavaScript to showcase skills, projects, and achievements.</p>
                </div>
                <div class="skill-card">
                    <h3>E-commerce Platform</h3>
                    <p>Enabled seamless online shopping experience and handled 100+ concurrent users during testing. Improved online presence and received positive feedback.</p>
                </div>
                <div class="skill-card">
                    <h3>Real-time Chat Website</h3>
                    <p>Made a working model of chatting website, including real-time data transmission technology.</p>
                </div>
                <div class="skill-card">
                    <h3>CCTV & WiFi Mesh Technology</h3>
                    <p>Worked on technology of closed circuit television and mesh technology of WiFi transmission.</p>
                </div>
            </div>
        </section>

        <section id="experience" class="section fade-in">
            <h2>Experience</h2>
            <div class="skill-card">
                <h3>Python Development</h3>
                <div style="font-weight: 600; color: #3498db; margin: 1rem 0;">Educational Institution</div>
                <p>• Created an engaging classroom atmosphere by encouraging open discussions about relevant topics in Python development trends</p>
                <p>• Conducted regular workshops focused on specific aspects of Python development like web frameworks or automation libraries</p>
            </div>
            <div class="skill-card">
                <h3>Web Developer</h3>
                <div style="font-weight: 600; color: #3498db; margin: 1rem 0;">Freelance</div>
                <p>• Coded websites using HTML, CSS, JavaScript, and jQuery languages</p>
                <p>• Planned website development, converting mockups into usable web presence with HTML, JavaScript, AJAX, and JSON coding</p>
            </div>
            <div class="skill-card">
                <h3>3D Designer</h3>
                <div style="font-weight: 600; color: #3498db; margin: 1rem 0;">Freelance</div>
                <p>• Enhanced 3D model quality by implementing advanced design techniques and software tools</p>
                <p>• Created detailed 3D models and designs for various projects</p>
            </div>
        </section>

        <section id="education" class="section fade-in">
            <h2>Education</h2>
            <div class="skill-card">
                <h3>Bachelor of Engineering: Information Technology</h3>
                <div style="font-weight: 600; color: #495057; margin: 0.5rem 0;">Shri Sant Gajanan Maharaj College of Engineering Shegaon</div>
                <div style="color: #6c757d; font-style: italic;">2028 | Shegaon Amravati</div>
            </div>
            <div class="skill-card">
                <h3>12th Standard</h3>
                <div style="font-weight: 600; color: #495057; margin: 0.5rem 0;">N.D. KOLHE</div>
                <div style="color: #6c757d; font-style: italic;">2022 | WASHIM</div>
            </div>
            <div class="skill-card">
                <h3>10th Standard</h3>
                <div style="font-weight: 600; color: #495057; margin: 0.5rem 0;">FATIMA CONVENT HIGH SCHOOL</div>
                <div style="color: #6c757d; font-style: italic;">2020 | AMRAVATI</div>
            </div>
            <div class="skill-card">
                <h3>Certifications</h3>
                <p>• Python Programming Certification</p>
                <p>• NPTL Biomolecule Engineering</p>
                <p>• IIT Madras BS DS</p>
            </div>
        </section>

        <section id="contact" class="section fade-in">
            <h2>Contact Me</h2>
            <div style="text-align: center;">
                <p style="font-size: 1.1rem; color: #6c757d; margin-bottom: 2rem;">I'm always open to discussing new opportunities and projects. Feel free to reach out!</p>
                <div style="display: flex; justify-content: center; gap: 2rem; margin-top: 2rem; flex-wrap: wrap;">
                    <a href="tel:+919067310965" class="skill-card" style="text-decoration: none; min-width: 200px;">
                        <strong style="color: #3498db; font-size: 1.1rem;">Phone</strong><br>
                        +91 90673 10965
                    </a>
                    <a href="mailto:kartikadmane11@gmail.com" class="skill-card" style="text-decoration: none; min-width: 200px;">
                        <strong style="color: #3498db; font-size: 1.1rem;">Email</strong><br>
                        kartikadmane11@gmail.com
                    </a>
                    <div class="skill-card" style="min-width: 200px;">
                        <strong style="color: #3498db; font-size: 1.1rem;">Location</strong><br>
                        Mumbai, 448605
                    </div>
                </div>
            </div>
        </section>
    </div>

    <footer style="background: #2c3e50; color: white; text-align: center; padding: 2rem 0; margin-top: 0;">
        <div class="container">
            <p>Developed by Kartik Admane © 2024</p>
        </div>
    </footer>

    <!-- Modal Structure -->
    <div id="skillModal" class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h2 id="modalTitle">Skill Documentation</h2>
                <span class="close">&times;</span>
            </div>
            <div class="modal-body" id="modalBody">
                <!-- Content will be dynamically loaded here -->
            </div>
        </div>
    </div>

    <script>
        // Skill documentation data
        const skillData = {
            python: {
                title: "Python Development",
                description: "Comprehensive Python development experience focusing on web frameworks, automation, and data analysis. I leverage Python's versatility to build robust backend systems, automate complex tasks, and perform insightful data analysis.",
                techStack: ["Python 3.x", "Django", "Flask", "FastAPI", "Pandas", "NumPy", "Requests", "BeautifulSoup", "Celery", "SQLAlchemy"],
                learnings: [
                    "Mastered object-oriented programming concepts in Python for scalable and maintainable code.",
                    "Learned to build scalable web applications using Django and Flask frameworks, including RESTful API development.",
                    "Developed skills in API development and integration, consuming third-party APIs and creating custom ones.",
                    "Gained expertise in data manipulation and analysis using Pandas and NumPy, including data cleaning and visualization.",
                    "Understanding of Python best practices and PEP 8 standards for writing clean, readable, and efficient code."
                ],
                projects: ["E-commerce Platform Backend", "Web Scraping Tools", "Data Analysis Scripts", "Task Automation Bots"],
                screenshots: ["python_project1.jpg", "python_project2.png", "python_project3.jpg"] // Placeholder for your images
            },
            web: {
                title: "Web Development",
                description: "Full-stack web development with modern technologies and responsive design principles. I create engaging and user-friendly web applications, ensuring optimal performance and cross-browser compatibility.",
                techStack: ["HTML5", "CSS3", "JavaScript (ES6+)", "jQuery", "AJAX", "JSON", "Bootstrap", "Responsive Design", "React.js (Basic)", "Sass"],
                learnings: [
                    "Mastered responsive web design principles to ensure seamless user experience across all devices.",
                    "Learned modern JavaScript ES6+ features for dynamic and interactive web applications.",
                    "Developed skills in creating interactive user interfaces with a focus on accessibility and usability.",
                    "Understanding of cross-browser compatibility issues and effective debugging techniques.",
                    "Expertise in optimizing web performance for faster loading times and improved user engagement."
                ],
                projects: ["Personal Portfolio Website", "E-commerce Frontend", "Real-time Chat Interface", "Interactive Data Dashboards"],
                screenshots: ["web_project1.jpg", "web_project2.png", "web_project3.jpg"] // Placeholder for your images
            },
            cyber: {
                title: "Cyber Security",
                description: "Security assessment, threat analysis, and implementation of robust security measures in applications and systems. My focus is on identifying vulnerabilities and building secure digital environments.",
                techStack: ["Security Auditing", "Penetration Testing", "Network Security", "Vulnerability Assessment", "Security Protocols (SSL/TLS)", "Firewalls", "Intrusion Detection Systems (IDS)"],
                learnings: [
                    "Understanding of common security vulnerabilities (OWASP Top 10) and how to mitigate them.",
                    "Learned penetration testing methodologies and ethical hacking techniques.",
                    "Developed skills in network security analysis, including traffic monitoring and anomaly detection.",
                    "Knowledge of secure coding practices to prevent common software vulnerabilities.",
                    "Experience with security tools and frameworks for threat intelligence and incident response."
                ],
                projects: ["Security Audit Reports", "Vulnerability Assessments", "Security Protocol Implementation", "Secure Web Application Development"],
                screenshots: ["cyber_project1.jpg", "cyber_project2.png", "cyber_project3.jpg"] // Placeholder for your images
            },
            mobile: {
                title: "Mobile App Development",
                description: "iOS application development with a strong focus on native app development and delivering exceptional user experiences. I build intuitive and high-performance mobile applications.",
                techStack: ["Swift", "iOS SDK", "Xcode", "UIKit", "Core Data", "Native Development", "Firebase (Basic)", "RESTful APIs"],
                learnings: [
                    "Mastered the iOS app development lifecycle from conception to deployment on the App Store.",
                    "Learned Swift programming language fundamentals and advanced concepts for robust app development.",
                    "Understanding of iOS Human Interface Guidelines to create visually appealing and user-friendly interfaces.",
                    "Experience with the App Store submission process, including provisioning profiles and certificates.",
                    "Knowledge of mobile app optimization techniques for performance, battery life, and data usage."
                ],
                projects: ["iOS Utility Apps", "Mobile UI Prototypes", "App Store Submissions", "Simple Game Development"],
                screenshots: ["mobile_project1.jpg", "mobile_project2.png", "mobile_project3.jpg"] // Placeholder for your images
            },
            "3d": { // Using quotes because '3d' is not a valid JS identifier without them
                title: "3D Design & CAD",
                description: "Advanced 3D modeling and design using professional CAD software like Fusion 360 for mechanical design, product prototyping, and visualization. I bring concepts to life in three dimensions.",
                techStack: ["Fusion 360", "3D Modeling", "CAD Design", "Technical Drawing", "Product Design", "Rendering", "Assembly Design"],
                learnings: [
                    "Mastered 3D modeling techniques and best practices for creating complex geometries.",
                    "Learned parametric design principles for flexible and easily modifiable models.",
                    "Developed skills in technical drawing and documentation according to industry standards.",
                    "Understanding of manufacturing constraints in design, optimizing for production methods.",
                    "Experience with design for 3D printing and other additive manufacturing processes."
                ],
                projects: ["Mechanical Components", "Product Prototypes", "Technical Drawings", "Custom Enclosures"],
                screenshots: ["3d_project1.jpg", "3d_project2.png", "3d_project3.jpg"] // Placeholder for your images
            },
            pcb: {
                title: "PCB Design",
                description: "Electronic circuit design and PCB layout using professional tools like KiCad for hardware development projects. I transform circuit diagrams into functional physical boards.",
                techStack: ["KiCad", "Circuit Design", "PCB Layout", "Schematic Design", "Electronics", "Component Selection", "Gerber Files", "Signal Integrity"],
                learnings: [
                    "Understanding of electronic circuit design principles and component functionality.",
                    "Learned PCB layout best practices and design rules for manufacturability and performance.",
                    "Experience with component selection and sourcing for various electronic applications.",
                    "Knowledge of manufacturing constraints for PCBs, including layer stack-up and trace impedance.",
                    "Skills in debugging and testing electronic circuits, from prototype to final product."
                ],
                projects: ["Custom PCB Designs", "Arduino Shield Development", "Sensor Interface Boards", "Power Management Modules"],
                screenshots: ["pcb_project1.jpg", "pcb_project2.png", "pcb_project3.jpg"] // Placeholder for your images
            },
            "3dprint": { // Using quotes because '3dprint' is not a valid JS identifier without them
                title: "3D Printing",
                description: "Expertise in 3D printing technology, encompassing prototyping, additive manufacturing, and optimizing designs for various printing methods. I turn digital models into physical objects.",
                techStack: ["FDM Printing", "SLA Printing", "Slicing Software (Cura, PrusaSlicer)", "3D Printer Maintenance", "Material Selection (PLA, ABS, PETG, Resin)", "Post-processing"],
                learnings: [
                    "Understanding of different 3D printing technologies (FDM, SLA) and their applications.",
                    "Learned optimal print settings for various materials to achieve desired part quality.",
                    "Developed skills in post-processing techniques for smooth finishes and functional parts.",
                    "Experience with 3D printer maintenance and troubleshooting common printing issues.",
                    "Knowledge of design for additive manufacturing (DfAM) principles for successful prints."
                ],
                projects: ["Functional Prototypes", "Custom Parts", "Educational Models", "Tooling and Jigs"],
                screenshots: ["3dprint_project1.jpg", "3dprint_project2.png", "3dprint_project3.jpg"] // Placeholder for your images
            },
            laser: {
                title: "Laser Cutting",
                description: "Precision laser cutting expertise for rapid prototyping, custom parts fabrication, and material processing with various materials like wood, acrylic, and paper. I create intricate designs with high accuracy.",
                techStack: ["Laser Cutting Machines", "Vector Design (Adobe Illustrator, Inkscape)", "Material Processing", "Precision Cutting", "CAD to Vector Conversion", "Engraving"],
                learnings: [
                    "Mastered laser cutting parameters for different materials to achieve clean cuts and engravings.",
                    "Learned vector design optimization for cutting efficiency and minimizing material waste.",
                    "Understanding of material properties and cutting limitations for various substrates.",
                    "Experience with kerf compensation and maintaining precision tolerances in designs.",
                    "Skills in post-processing and finishing techniques for laser-cut parts."
                ],
                projects: ["Custom Enclosures", "Precision Parts", "Decorative Elements", "Stencils and Templates"],
                screenshots: ["laser_project1.jpg", "laser_project2.png", "laser_project3.jpg"] // Placeholder for your images
            },
            database: {
                title: "Database & Tools",
                description: "Database management and version control expertise using industry-standard tools and practices. I ensure data integrity, efficient storage, and collaborative code development.",
                techStack: ["SQL", "MySQL", "PostgreSQL", "Git", "GitHub", "Database Design", "Version Control", "ERD (Entity-Relationship Diagrams)", "SQLAlchemy"],
                learnings: [
                    "Mastered SQL query optimization and efficient database design principles.",
                    "Learned Git workflow and collaborative development practices for team projects.",
                    "Understanding of database normalization principles and data integrity constraints.",
                    "Experience with database backup and recovery procedures to prevent data loss.",
                    "Skills in code versioning and project management using Git and GitHub."
                ],
                projects: ["Database Schema Design", "Data Migration Scripts", "Repository Management", "SQL Reporting Tools"],
                screenshots: ["database_project1.jpg", "database_project2.png", "database_project3.jpg"] // Placeholder for your images
            },
            languages: {
                title: "Languages",
                description: "Multilingual communication abilities enabling effective collaboration in diverse environments. I can communicate technical and non-technical information clearly across different linguistic contexts.",
                techStack: ["English", "Hindi", "Marathi", "Technical Communication", "Documentation", "Presentation Skills", "Cross-cultural Communication"],
                learnings: [
                    "Effective communication in multiple languages for broader reach and understanding.",
                    "Technical documentation skills in English, ensuring clarity and accuracy.",
                    "Cross-cultural communication experience, fostering inclusive interactions.",
                    "Presentation skills in various languages, adapting content for different audiences.",
                    "Understanding of translation and localization principles for global projects."
                ],
                projects: ["Technical Documentation", "Multilingual Presentations", "Cross-cultural Project Communication", "Localized Content Creation"],
                screenshots: ["languages_project1.jpg", "languages_project2.png", "languages_project3.jpg"] // Placeholder for your images
            }
        };

        // Modal functionality
        function openModal(skillKey) {
            const modal = document.getElementById('skillModal');
            const modalTitle = document.getElementById('modalTitle');
            const modalBody = document.getElementById('modalBody');
            
            const skill = skillData[skillKey];
            if (!skill) {
                console.error("Skill data not found for key:", skillKey);
                return;
            }
            
            modalTitle.textContent = skill.title;
            
            modalBody.innerHTML = `
                <div class="documentation-section">
                    <h3>📋 Description</h3>
                    <p>${skill.description}</p>
                </div>
                
                <div class="documentation-section">
                    <h3>🛠️ Tech Stack</h3>
                    <div class="tech-stack">
                        ${skill.techStack.map(tech => `<span class="tech-tag">${tech}</span>`).join('')}
                    </div>
                </div>
                
                <div class="documentation-section">
                    <h3>📸 Screenshots/Results</h3>
                    <div class="screenshot-gallery">
                        ${skill.screenshots.map(screenshot => `
                            <div class="screenshot">
                                <img src="images/${screenshot}" alt="${screenshot.replace(/_/g, ' ').replace(/\..*/, '')}" onerror="this.onerror=null;this.src='https://via.placeholder.com/200x150?text=Image+Not+Found';" />
                            </div>
                        `).join('')}
                    </div>
                </div>
                
                <div class="documentation-section">
                    <h3>🚀 Key Projects</h3>
                    <ul style="list-style: none; padding: 0;">
                        ${skill.projects.map(project => `
                            <li style="background: #f8f9fa; margin: 0.5rem 0; padding: 1rem; border-left: 4px solid #3498db; border-radius: 0 8px 8px 0;">
                                🎯 ${project}
                            </li>
                        `).join('')}
                    </ul>
                </div>
                
                <div class="documentation-section">
                    <h3>💡 Key Learnings</h3>
                    <ul class="learning-points">
                        ${skill.learnings.map(learning => `<li>${learning}</li>`).join('')}
                    </ul>
                </div>
            `;
            
            modal.style.display = 'block';
            document.body.style.overflow = 'hidden'; // Prevent scrolling on body when modal is open
        }

        // Close modal functionality
        function closeModal() {
            const modal = document.getElementById('skillModal');
            modal.style.display = 'none';
            document.body.style.overflow = 'auto'; // Restore scrolling on body
        }

        // Event listeners
        document.addEventListener('DOMContentLoaded', function() {
            // Close modal when clicking the X
            document.querySelector('.close').addEventListener('click', closeModal);
            
            // Close modal when clicking outside
            document.getElementById('skillModal').addEventListener('click', function(e) {
                if (e.target === this) {
                    closeModal();
                }
            });
            
            // Close modal with Escape key
            document.addEventListener('keydown', function(e) {
                if (e.key === 'Escape') {
                    closeModal();
                }
            });
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Header background on scroll
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.background = 'rgba(255, 255, 255, 0.98)';
                header.style.boxShadow = '0 4px 30px rgba(0, 0, 0, 0.1)';
            } else {
                header.style.background = 'rgba(255, 255, 255, 0.95)';
                header.style.boxShadow = '0 2px 20px rgba(0, 0, 0, 0.1)';
            }
        });

        // Animate elements on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        // Observe all sections with fade-in class
        document.querySelectorAll('.fade-in').forEach(section => {
            observer.observe(section);
        });
    </script>
</body>
</html>
