# Learn-connet-
Helping students collaborate and learn 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LearnConnect - Student Learning & Collaboration Platform</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary: #4361ee;
            --secondary: #3f37c9;
            --accent: #4cc9f0;
            --light: #f8f9fa;
            --dark: #212529;
            --success: #4ade80;
            --warning: #facc15;
            --danger: #f87171;
        }

        body {
            background-color: #f5f7fb;
            color: var(--dark);
            line-height: 1.6;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }

        /* Header Styles */
        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 1rem 0;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 1.8rem;
            font-weight: 700;
        }

        .logo i {
            color: var(--accent);
        }

        .nav-links {
            display: flex;
            gap: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
        }

        .nav-links a:hover {
            color: var(--accent);
        }

        .auth-buttons {
            display: flex;
            gap: 1rem;
        }

        .btn {
            padding: 0.6rem 1.2rem;
            border-radius: 30px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            border: none;
        }

        .btn-outline {
            background: transparent;
            border: 2px solid white;
            color: white;
        }

        .btn-outline:hover {
            background: white;
            color: var(--primary);
        }

        .btn-primary {
            background: var(--accent);
            color: white;
        }

        .btn-primary:hover {
            background: #3ab9e0;
            transform: translateY(-2px);
        }

        /* Hero Section */
        .hero {
            padding: 5rem 0;
            background: url('https://images.unsplash.com/photo-1523240795612-9a054b0db644?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80') no-repeat center center/cover;
            position: relative;
            color: white;
            text-align: center;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
        }

        .hero-content {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
            padding: 2rem;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            text-shadow: 0 2px 4px rgba(0,0,0,0.3);
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        /* Features Section */
        .section {
            padding: 5rem 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
        }

        .section-title h2 {
            font-size: 2.5rem;
            color: var(--primary);
            margin-bottom: 1rem;
        }

        .section-title p {
            color: #666;
            max-width: 600px;
            margin: 0 auto;
        }

        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .feature-card {
            background: white;
            border-radius: 10px;
            padding: 2rem;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: transform 0.3s ease;
        }

        .feature-card:hover {
            transform: translateY(-10px);
        }

        .feature-icon {
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, var(--primary), var(--accent));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 1.5rem;
            color: white;
            font-size: 2rem;
        }

        .feature-card h3 {
            margin-bottom: 1rem;
            color: var(--dark);
        }

        /* Subjects Section */
        .subjects {
            background: var(--light);
        }

        .subject-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
        }

        .subject-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: all 0.3s ease;
        }

        .subject-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }

        .subject-img {
            height: 150px;
            background: linear-gradient(45deg, var(--primary), var(--accent));
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
        }

        .subject-content {
            padding: 1.5rem;
        }

        .subject-content h3 {
            margin-bottom: 0.5rem;
        }

        .subject-content p {
            color: #666;
            margin-bottom: 1rem;
        }

        .subject-stats {
            display: flex;
            justify-content: space-between;
            color: #666;
            font-size: 0.9rem;
        }

        /* Collaboration Section */
        .collaboration-tools {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .tool-card {
            background: white;
            border-radius: 10px;
            padding: 2rem;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }

        .tool-card h3 {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 1rem;
            color: var(--primary);
        }

        /* Testimonials */
        .testimonials {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            text-align: center;
        }

        .testimonials .section-title h2 {
            color: white;
        }

        .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .testimonial-card {
            background: rgba(255,255,255,0.1);
            border-radius: 10px;
            padding: 2rem;
            backdrop-filter: blur(10px);
        }

        .testimonial-card .quote {
            font-size: 1.2rem;
            margin-bottom: 1rem;
            font-style: italic;
        }

        .testimonial-card .author {
            font-weight: 600;
            color: var(--accent);
        }

        /* CTA Section */
        .cta {
            text-align: center;
            padding: 4rem 0;
            background: var(--light);
        }

        .cta h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: var(--primary);
        }

        .cta p {
            max-width: 600px;
            margin: 0 auto 2rem;
            color: #666;
        }

        /* Footer */
        footer {
            background: var(--dark);
            color: white;
            padding: 3rem 0 1rem;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .footer-column h3 {
            margin-bottom: 1rem;
            color: var(--accent);
        }

        .footer-column ul {
            list-style: none;
        }

        .footer-column ul li {
            margin-bottom: 0.5rem;
        }

        .footer-column ul li a {
            color: #ccc;
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-column ul li a:hover {
            color: var(--accent);
        }

        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-links a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background: #333;
            border-radius: 50%;
            color: white;
            transition: all 0.3s ease;
        }

        .social-links a:hover {
            background: var(--primary);
            transform: translateY(-3px);
        }

        .copyright {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid #333;
            color: #ccc;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .navbar {
                flex-direction: column;
                gap: 1rem;
            }
            
            .nav-links {
                gap: 1rem;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .section {
                padding: 3rem 0;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <nav class="navbar">
                <div class="logo">
                    <i class="fas fa-graduation-cap"></i>
                    <span>LearnConnect</span>
                </div>
                <div class="nav-links">
                    <a href="#features">Features</a>
                    <a href="#subjects">Subjects</a>
                    <a href="#collaborate">Collaborate</a>
                    <a href="#testimonials">Testimonials</a>
                </div>
                <div class="auth-buttons">
                    <button class="btn btn-outline">Login</button>
                    <button class="btn btn-primary">Sign Up</button>
                </div>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>Learn Together, Grow Together</h1>
            <p>Join a vibrant community of students to learn, collaborate, and achieve academic success through interactive tools and peer support.</p>
            <button class="btn btn-primary" style="font-size: 1.1rem; padding: 0.8rem 2rem;">Start Learning Today</button>
        </div>
    </section>

    <!-- Features Section -->
    <section class="section" id="features">
        <div class="container">
            <div class="section-title">
                <h2>Powerful Learning Features</h2>
                <p>Everything you need to succeed in your studies and collaborate with peers</p>
            </div>
            <div class="features">
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-book-open"></i>
                    </div>
                    <h3>Interactive Lessons</h3>
                    <p>Engage with multimedia content, quizzes, and interactive exercises to enhance your learning experience.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-comments"></i>
                    </div>
                    <h3>Study Groups</h3>
                    <p>Join or create study groups with classmates to discuss topics, share resources, and prepare for exams.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <i class="fas fa-chalkboard-teacher"></i>
                    </div>
                    <h3>Virtual Classrooms</h3>
                    <p>Participate in live sessions, attend virtual lectures, and interact with instructors in real-time.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Subjects Section -->
    <section class="section subjects" id="subjects">
        <div class="container">
            <div class="section-title">
                <h2>Popular Subjects</h2>
                <p>Explore courses and resources across various academic disciplines</p>
            </div>
            <div class="subject-grid">
                <div class="subject-card">
                    <div class="subject-img">
                        <i class="fas fa-calculator"></i>
                    </div>
                    <div class="subject-content">
                        <h3>Mathematics</h3>
                        <p>Algebra, Calculus, Statistics, and more</p>
                        <div class="subject-stats">
                            <span><i class="fas fa-users"></i> 12,500 learners</span>
                            <span><i class="fas fa-graduation-cap"></i> 45 courses</span>
                        </div>
                    </div>
                </div>
                <div class="subject-card">
                    <div class="subject-img">
                        <i class="fas fa-flask"></i>
                    </div>
                    <div class="subject-content">
                        <h3>Science</h3>
                        <p>Physics, Chemistry, Biology, and more</p>
                        <div class="subject-stats">
                            <span><i class="fas fa-users"></i> 9,800 learners</span>
                            <span><i class="fas fa-graduation-cap"></i> 38 courses</span>
                        </div>
                    </div>
                </div>
                <div class="subject-card">
                    <div class="subject-img">
                        <i class="fas fa-laptop-code"></i>
                    </div>
                    <div class="subject-content">
                        <h3>Computer Science</h3>
                        <p>Programming, Algorithms, Web Development</p>
                        <div class="subject-stats">
                            <span><i class="fas fa-users"></i> 15,200 learners</span>
                            <span><i class="fas fa-graduation-cap"></i> 52 courses</span>
                        </div>
                    </div>
                </div>
                <div class="subject-card">
                    <div class="subject-img">
                        <i class="fas fa-language"></i>
                    </div>
                    <div class="subject-content">
                        <h3>Languages</h3>
                        <p>English, Spanish, French, Mandarin</p>
                        <div class="subject-stats">
                            <span><i class="fas fa-users"></i> 8,700 learners</span>
                            <span><i class="fas fa-graduation-cap"></i> 29 courses</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Collaboration Section -->
    <section class="section" id="collaborate">
        <div class="container">
            <div class="section-title">
                <h2>Collaboration Tools</h2>
                <p>Work together with your peers using our integrated collaboration features</p>
            </div>
            <div class="collaboration-tools">
                <div class="tool-card">
                    <h3><i class="fas fa-users"></i> Group Projects</h3>
                    <p>Collaborate on assignments, share documents, and track progress with your team members.</p>
                </div>
                <div class="tool-card">
                    <h3><i class="fas fa-comments"></i> Discussion Forums</h3>
                    <p>Engage in meaningful discussions, ask questions, and share knowledge with fellow students.</p>
                </div>
                <div class="tool-card">
                    <h3><i class="fas fa-video"></i> Study Sessions</h3>
                    <p>Schedule and participate in virtual study sessions with classmates around the world.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section class="section testimonials" id="testimonials">
        <div class="container">
            <div class="section-title">
                <h2>Student Success Stories</h2>
                <p>Hear from students who have transformed their learning experience</p>
            </div>
            <div class="testimonial-grid">
                <div class="testimonial-card">
                    <div class="quote">"LearnConnect helped me connect with classmates and form study groups that significantly improved my grades. The collaborative tools are amazing!"</div>
                    <div class="author">- Sarah Johnson, Computer Science Student</div>
                </div>
                <div class="testimonial-card">
                    <div class="quote">"I was struggling with calculus, but the study groups and peer support on this platform made all the difference. Highly recommended!"</div>
                    <div class="author">- Michael Chen, Mathematics Student</div>
                </div>
                <div class="testimonial-card">
                    <div class="quote">"The interactive lessons and real-time collaboration features have made learning so much more engaging and effective for me."</div>
                    <div class="author">- Emma Rodriguez, Biology Student</div>
                </div>
            </div>
        </div>
    </section>

    <!-- CTA Section -->
    <section class="cta">
        <div class="container">
            <h2>Ready to Transform Your Learning Experience?</h2>
            <p>Join thousands of students who are already learning and collaborating together on LearnConnect</p>
            <button class="btn btn-primary" style="font-size: 1.1rem; padding: 0.8rem 2rem;">Get Started Free</button>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>LearnConnect</h3>
                    <p>The ultimate platform for students to learn, collaborate, and succeed together.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                    </div>
                </div>
                <div class="footer-column">
                    <h3>Quick Links</h3>
                    <ul>
                        <li><a href="#">Home</a></li>
                        <li><a href="#features">Features</a></li>
                        <li><a href="#subjects">Subjects</a></li>
                        <li><a href="#collaborate">Collaborate</a></li>
                        <li><a href="#testimonials">Testimonials</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Resources</h3>
                    <ul>
                        <li><a href="#">Blog</a></li>
                        <li><a href="#">Help Center</a></li>
                        <li><a href="#">Community Guidelines</a></li>
                        <li><a href="#">Tutorials</a></li>
                        <li><a href="#">Webinars</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Support</h3>
                    <ul>
                        <li><a href="#">Contact Us</a></li>
                        <li><a href="#">FAQ</a></li>
                        <li><a href="#">Privacy Policy</a></li>
                        <li><a href="#">Terms of Service</a></li>
                        <li><a href="#">Accessibility</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2025 LearnConnect. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Simple JavaScript for interactive elements
        document.addEventListener('DOMContentLoaded', function() {
            // Add hover effects to cards
            const cards = document.querySelectorAll('.feature-card, .subject-card, .tool-card');
            cards.forEach(card => {
                card.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateY(-10px)';
                });
                card.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateY(0)';
                });
            });

            // Smooth scrolling for navigation links
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    document.querySelector(this.getAttribute('href')).scrollIntoView({
                        behavior: 'smooth'
                    });
                });
            });

            // Button hover effects
            const buttons = document.querySelectorAll('.btn');
            buttons.forEach(button => {
                button.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateY(-2px)';
                });
                button.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateY(0)';
                });
            });
        });
    </script>
</body>
</html>
