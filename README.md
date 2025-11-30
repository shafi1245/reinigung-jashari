<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
5    <meta name="viewport" content="width=device-width, initial-scale=1.0">
6    <title>ReinigungsService Jashari - Professionelle Reinigung in Gelsenkirchen</title>
7    <link rel="icon" type="image/x-icon" href="favicon.ico">
8    <link rel="shortcut icon" type="image/x-icon" href="favicon.ico">
9    <link rel="apple-touch-icon" href="favicon.ico">
10    <link rel="preconnect" href="https://fonts.googleapis.com">
11    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
12    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            line-height: 1.6;
            color: #1e293b;
            overflow-x: hidden;
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

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0px);
            }
            50% {
                transform: translateY(-20px);
            }
        }

        @keyframes shine {
            0% {
                left: -100%;
            }
            100% {
                left: 100%;
            }
        }

        /* Cookie Banner Styles */
        .cookie-banner {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.5);
            z-index: 10000;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 1rem;
        }

        .cookie-banner.hidden {
            display: none;
        }

        .cookie-content {
            background: white;
            border-radius: 20px;
            max-width: 600px;
            width: 100%;
            max-height: 90vh;
            overflow-y: auto;
            position: relative;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
        }

        .cookie-header {
            padding: 2rem 2rem 1rem;
            border-bottom: 1px solid #e2e8f0;
            position: relative;
        }

        .cookie-close {
            position: absolute;
            top: 1.5rem;
            right: 1.5rem;
            background: none;
            border: none;
            font-size: 2rem;
            cursor: pointer;
            color: #64748b;
            line-height: 1;
            padding: 0;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
        }

        .cookie-close:hover {
            color: #1e293b;
            transform: rotate(90deg);
        }

        .cookie-header h2 {
            font-size: 1.8rem;
            color: #1e293b;
            margin-bottom: 0;
        }

        .cookie-body {
            padding: 2rem;
        }

        .cookie-body p {
            color: #64748b;
            margin-bottom: 1.5rem;
            line-height: 1.7;
        }

        .cookie-section {
            margin-bottom: 1.5rem;
        }

        .cookie-links {
            display: flex;
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .cookie-links a {
            color: #2563eb;
            text-decoration: underline;
            font-weight: 500;
            transition: color 0.3s;
        }

        .cookie-links a:hover {
            color: #1d4ed8;
        }

        .cookie-toggle {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 1.2rem;
            background: #f8fafc;
            border-radius: 12px;
            margin-bottom: 1rem;
        }

        .cookie-toggle span {
            color: #1e293b;
            font-weight: 500;
            font-size: 1rem;
        }

        .toggle-switch {
            position: relative;
            width: 60px;
            height: 32px;
            background: #cbd5e1;
            border-radius: 16px;
            cursor: pointer;
            transition: background 0.3s;
        }

        .toggle-switch.disabled {
            opacity: 0.5;
            cursor: not-allowed;
        }

        .toggle-switch::after {
            content: '';
            position: absolute;
            top: 4px;
            left: 4px;
            width: 24px;
            height: 24px;
            background: white;
            border-radius: 50%;
            transition: transform 0.3s;
        }

        .toggle-switch.active {
            background: #2563eb;
        }

        .toggle-switch.active::after {
            transform: translateX(28px);
        }

        .cookie-buttons {
            display: flex;
            flex-direction: column;
            gap: 0.8rem;
            margin-top: 2rem;
        }

        .cookie-btn {
            padding: 1rem 2rem;
            border: none;
            border-radius: 12px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            font-family: 'Poppins', sans-serif;
        }

        .cookie-btn-primary {
            background: #1e293b;
            color: white;
        }

        .cookie-btn-primary:hover {
            background: #0f172a;
            transform: translateY(-2px);
        }

        .cookie-btn-secondary {
            background: #1e293b;
            color: white;
        }

        .cookie-btn-secondary:hover {
            background: #334155;
            transform: translateY(-2px);
        }

        .cookie-btn-tertiary {
            background: white;
            color: #1e293b;
            border: 2px solid #e2e8f0;
        }

        .cookie-btn-tertiary:hover {
            background: #f8fafc;
            border-color: #cbd5e1;
        }

        .more-info {
            margin-top: 1.5rem;
            padding-top: 1.5rem;
            border-top: 1px solid #e2e8f0;
        }

        .more-info h3 {
            font-size: 1rem;
            color: #1e293b;
            margin-bottom: 0.5rem;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .more-info-content {
            display: none;
            margin-top: 1rem;
            color: #64748b;
            font-size: 0.95rem;
            line-height: 1.7;
        }

        .more-info-content.visible {
            display: block;
        }

        .arrow {
            transition: transform 0.3s;
        }

        .arrow.rotated {
            transform: rotate(180deg);
        }

        /* Navigation */
        nav {
            background: rgba(255, 255, 255, 0.98);
            padding: 1.2rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 20px rgba(0,0,0,0.1);
            backdrop-filter: blur(10px);
        }

        nav .container {
            max-width: 1300px;
            margin: 0 auto;
            padding: 0 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        nav .logo {
            font-size: 1.6rem;
            font-weight: 800;
            background: linear-gradient(135deg, #2563eb, #3b82f6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            cursor: pointer;
            transition: all 0.3s;
        }

        nav .logo:hover {
            transform: scale(1.05);
        }

        nav .logo-link {
            display: flex;
            align-items: center;
            transition: all 0.3s;
        }

        nav .logo-link:hover {
            transform: scale(1.05);
        }

        nav .logo-img {
    height: 80px;
    width: auto;
    display: block;
    background: transparent;
}

        nav ul {
            display: flex;
            list-style: none;
            gap: 2.5rem;
        }

        nav a {
            text-decoration: none;
            color: #1e293b;
            font-weight: 500;
            transition: all 0.3s;
            position: relative;
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: #2563eb;
            transition: width 0.3s;
        }

        nav a:hover::after {
            width: 100%;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(0, 0, 0, 0.35), rgba(0, 0, 0, 0.35)),
                        url('https://images.unsplash.com/photo-1581578731548-c64695cc6952?w=1920&q=80');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 30% 50%, rgba(255,255,255,0.05), transparent);
        }

        .hero-content {
            max-width: 900px;
            padding: 2rem;
            position: relative;
            z-index: 1;
            animation: fadeInUp 1s ease-out;
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 1.5rem;
            font-weight: 800;
            text-shadow: 3px 3px 15px rgba(0,0,0,0.5);
            letter-spacing: -1px;
        }

        .hero .tagline {
            font-size: 1.6rem;
            margin-bottom: 3rem;
            font-weight: 300;
            text-shadow: 2px 2px 8px rgba(0,0,0,0.5);
            font-style: italic;
        }

        .cta-buttons {
            display: flex;
            gap: 1.5rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            padding: 1.2rem 2.5rem;
            font-size: 1.1rem;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            text-decoration: none;
            transition: all 0.3s;
            font-weight: 600;
            display: inline-block;
            position: relative;
            overflow: hidden;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: left 0.5s;
        }

        .btn:hover::before {
            left: 100%;
        }

        .btn-primary {
            background: white;
            color: #2563eb;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.4);
        }

        .btn-secondary {
            background: rgba(255,255,255,0.15);
            color: white;
            border: 2px solid white;
            backdrop-filter: blur(10px);
        }

        .btn-secondary:hover {
            background: white;
            color: #2563eb;
            transform: translateY(-3px);
        }

        /* Stats Section */
        .stats {
            background: linear-gradient(135deg, #1e293b, #334155);
            padding: 4rem 0;
            color: white;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 3rem;
            max-width: 1300px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .stat-item {
            text-align: center;
            animation: fadeInUp 0.8s ease-out;
        }

        .stat-number {
            font-size: 3.5rem;
            font-weight: 800;
            background: linear-gradient(135deg, #60a5fa, #3b82f6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 0.5rem;
        }

        .stat-label {
            font-size: 1.1rem;
            opacity: 0.9;
            font-weight: 300;
        }

        /* Container */
        .container {
            max-width: 1300px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        /* Section Styling */
        section {
            padding: 6rem 0;
        }

        .section-title {
            text-align: center;
            font-size: 2.8rem;
            margin-bottom: 1rem;
            color: #1e293b;
            font-weight: 700;
        }

        .section-subtitle {
            text-align: center;
            font-size: 1.2rem;
            color: #64748b;
            margin-bottom: 4rem;
            font-weight: 300;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, #2563eb, #3b82f6);
            margin: 1.5rem auto;
            border-radius: 2px;
        }

        /* Services Section */
        .services {
            background: linear-gradient(180deg, #f8fafc 0%, white 100%);
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2.5rem;
            margin-top: 3rem;
        }

        .service-card {
            background: white;
            padding: 2.5rem;
            border-radius: 20px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            border: 1px solid #e2e8f0;
            position: relative;
            overflow: hidden;
        }

        .service-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(90deg, #2563eb, #3b82f6);
            transform: scaleX(0);
            transition: transform 0.4s;
        }

        .service-card:hover::before {
            transform: scaleX(1);
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(37, 99, 235, 0.15);
        }

        .service-icon {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            display: inline-block;
            animation: float 3s ease-in-out infinite;
        }

        .service-card h3 {
            color: #1e293b;
            margin-bottom: 1rem;
            font-size: 1.5rem;
            font-weight: 600;
        }

        .service-card p {
            color: #64748b;
            line-height: 1.8;
        }

        /* Gallery Section */
        .gallery {
            background: white;
        }

        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem;
            margin-top: 3rem;
        }

        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 15px;
            height: 300px;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }

        .gallery-item:hover img {
            transform: scale(1.1);
        }

        .gallery-overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(to top, rgba(0,0,0,0.8), transparent);
            padding: 2rem;
            transform: translateY(100%);
            transition: transform 0.4s;
            color: white;
        }

        .gallery-item:hover .gallery-overlay {
            transform: translateY(0);
        }

        /* About Section */
        .about {
            background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)),
                        url('https://images.unsplash.com/photo-1628177142898-93e36e4e3a50?w=1920&q=80');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            color: white;
            position: relative;
        }

        .about::before {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml,<svg width="100" height="100" xmlns="http://www.w3.org/2000/svg"><circle cx="50" cy="50" r="2" fill="white" opacity="0.1"/></svg>');
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
            position: relative;
            z-index: 1;
        }

        .about h2 {
            color: white;
        }

        .about-text {
            font-size: 1.15rem;
            line-height: 1.9;
            font-weight: 300;
        }

        .about-text p {
            margin-bottom: 1.5rem;
        }

        .about-features {
            display: grid;
            gap: 1.5rem;
        }

        .feature-item {
            display: flex;
            align-items: start;
            gap: 1.5rem;
            background: rgba(255, 255, 255, 0.15);
            padding: 2rem;
            border-radius: 15px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255,255,255,0.2);
            transition: all 0.3s;
        }

        .feature-item:hover {
            background: rgba(255, 255, 255, 0.25);
            transform: translateX(10px);
        }

        .feature-icon {
            font-size: 2.5rem;
            flex-shrink: 0;
        }

        .feature-item h3 {
            margin-bottom: 0.5rem;
            font-size: 1.3rem;
        }

        /* Testimonials Section */
        .testimonials {
            background: linear-gradient(180deg, #f8fafc 0%, white 100%);
        }

        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2.5rem;
            margin-top: 3rem;
        }

        .testimonial-card {
            background: white;
            padding: 2.5rem;
            border-radius: 20px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            position: relative;
            border: 1px solid #e2e8f0;
            transition: all 0.3s;
        }

        .testimonial-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.12);
        }

        .testimonial-card::before {
            content: '"';
            font-size: 5rem;
            position: absolute;
            top: 1rem;
            left: 1.5rem;
            color: #2563eb;
            opacity: 0.2;
            font-family: Georgia, serif;
        }

        .testimonial-text {
            font-style: italic;
            color: #64748b;
            margin-bottom: 1.5rem;
            line-height: 1.8;
            position: relative;
            z-index: 1;
        }

        .testimonial-author {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .author-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: linear-gradient(135deg, #2563eb, #3b82f6);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: 600;
            font-size: 1.2rem;
        }

        .author-info h4 {
            color: #1e293b;
            font-size: 1.1rem;
        }

        .author-info p {
            color: #64748b;
            font-size: 0.9rem;
        }

        .stars {
            color: #fbbf24;
            margin-bottom: 1rem;
            font-size: 1.2rem;
        }

        /* Contact Section */
        .contact {
            background: white;
        }

        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            margin-top: 3rem;
        }

        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }

        .contact-item {
            display: flex;
            align-items: start;
            gap: 1.5rem;
            padding: 2rem;
            background: linear-gradient(135deg, #f8fafc, #f1f5f9);
            border-radius: 15px;
            transition: all 0.3s;
            border: 1px solid #e2e8f0;
        }

        .contact-item:hover {
            background: linear-gradient(135deg, #dbeafe, #bfdbfe);
            transform: translateX(10px);
            box-shadow: 0 10px 25px rgba(37, 99, 235, 0.1);
        }

        .contact-icon {
            font-size: 2rem;
            color: #2563eb;
            background: white;
            padding: 1rem;
            border-radius: 12px;
            box-shadow: 0 4px 10px rgba(37, 99, 235, 0.1);
        }

        .contact-item h3 {
            color: #1e293b;
            margin-bottom: 0.5rem;
            font-size: 1.3rem;
        }

        .contact-item a {
            color: #2563eb;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
        }

        .contact-item a:hover {
            color: #1d4ed8;
        }

        .contact-form {
            background: linear-gradient(135deg, #f8fafc, #f1f5f9);
            padding: 3rem;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.08);
            border: 1px solid #e2e8f0;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
            color: #1e293b;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            border: 2px solid #e2e8f0;
            border-radius: 10px;
            font-size: 1rem;
            transition: all 0.3s;
            font-family: 'Poppins', sans-serif;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #2563eb;
            box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.1);
        }

        .form-group textarea {
            min-height: 150px;
            resize: vertical;
        }

        /* Legal Pages Styling */
        .legal-page {
            background: white;
            padding: 8rem 0 6rem;
        }

        .legal-content {
            max-width: 900px;
            margin: 0 auto;
            background: white;
            padding: 3rem;
            border-radius: 20px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            border: 1px solid #e2e8f0;
        }

        .legal-content h1 {
            color: #1e293b;
            font-size: 2.5rem;
            margin-bottom: 2rem;
            padding-bottom: 1rem;
            border-bottom: 3px solid #2563eb;
        }

        .legal-content h2 {
            color: #1e293b;
            font-size: 1.8rem;
            margin-top: 2.5rem;
            margin-bottom: 1rem;
        }

        .legal-content h3 {
            color: #334155;
            font-size: 1.3rem;
            margin-top: 1.5rem;
            margin-bottom: 0.8rem;
        }

        .legal-content p {
            color: #64748b;
            line-height: 1.9;
            margin-bottom: 1.2rem;
        }

        .legal-content ul {
            margin-left: 2rem;
            margin-bottom: 1.5rem;
        }

        .legal-content li {
            color: #64748b;
            line-height: 1.9;
            margin-bottom: 0.5rem;
        }

        .legal-content strong {
            color: #1e293b;
        }

        .back-link {
            display: inline-block;
            margin-bottom: 2rem;
            color: #2563eb;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s;
        }

        .back-link:hover {
            color: #1d4ed8;
            transform: translateX(-5px);
        }

        /* Footer */
        footer {
            background: linear-gradient(135deg, #1e293b, #0f172a);
            color: white;
            padding: 4rem 0 1.5rem;
            position: relative;
            overflow: hidden;
        }

        footer::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, #2563eb, #3b82f6, #2563eb);
            background-size: 200% 100%;
            animation: shine 3s linear infinite;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
            margin-bottom: 3rem;
        }

        .footer-section h3 {
            color: #3b82f6;
            margin-bottom: 1.5rem;
            font-size: 1.3rem;
        }

        .footer-section p {
            color: #cbd5e1;
            line-height: 1.8;
            margin-bottom: 0.8rem;
        }

        .footer-section a {
            color: #cbd5e1;
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-section a:hover {
            color: #3b82f6;
        }

        .footer-links {
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
        }

        .footer-bottom {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid #334155;
            color: #94a3b8;
        }

        .footer-legal-links {
            margin-top: 1rem;
            display: flex;
            justify-content: center;
            gap: 2rem;
            flex-wrap: wrap;
        }

        .footer-legal-links a {
            color: #94a3b8;
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-legal-links a:hover {
            color: #3b82f6;
        }

        /* Responsive */
        @media (max-width: 968px) {
            nav ul {
                display: none;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero .tagline {
                font-size: 1.3rem;
            }

            .about-content,
            .contact-grid {
                grid-template-columns: 1fr;
            }

            .services-grid,
            .testimonials-grid {
                grid-template-columns: 1fr;
            }

            .stats-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .legal-content {
                padding: 2rem 1.5rem;
            }

            .cookie-content {
                max-width: 100%;
                border-radius: 0;
                max-height: 100vh;
            }

            .cookie-body {
                padding: 1.5rem;
            }

            .cookie-header {
                padding: 1.5rem;
            }
        }

        /* Smooth Scroll */
        html {
            scroll-behavior: smooth;
        }

        /* Scroll to top button */
        .scroll-top {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            background: linear-gradient(135deg, #2563eb, #3b82f6);
            color: white;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            cursor: pointer;
            box-shadow: 0 5px 20px rgba(37, 99, 235, 0.4);
            opacity: 0;
            transition: all 0.3s;
            z-index: 999;
        }

        .scroll-top.visible {
            opacity: 1;
        }

        .scroll-top:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(37, 99, 235, 0.5);
        }

        /* Hide all sections except the one with matching hash */
        body:not(.show-legal) .legal-page {
            display: none;
        }

        body.show-legal section:not(.legal-page) {
            display: none;
        }

        body.show-legal nav,
        body.show-legal footer {
            display: block;
        }
    </style>
</head>
<body>
    <!-- Cookie Banner -->
    <div id="cookieBanner" class="cookie-banner">
        <div class="cookie-content">
            <div class="cookie-header">
                <h2>Cookie-Richtlinie</h2>
                <button class="cookie-close" onclick="closeCookieBanner()">&times;</button>
            </div>
            <div class="cookie-body">
                <p>Diese Website verwendet Cookies. Weitere Informationen zu den Cookie-Arten finden sich unter den jeweiligen Kategorien. Dort lassen sich auch einzelne Cookies aktivieren. Die Cookie-Einstellungen können jederzeit über den Link im Footer dieser Website angepasst werden.</p>
                
                <div class="cookie-section">
                    <div class="cookie-links">
                        <a href="#impressum" onclick="showLegalPage('impressum'); closeCookieBanner();">Impressum</a>
                        <a href="#datenschutz" onclick="showLegalPage('datenschutz'); closeCookieBanner();">Datenschutz</a>
                    </div>
                </div>

                <div class="cookie-section">
                    <div class="cookie-toggle">
                        <span>Unbedingt erforderlich</span>
                        <div class="toggle-switch active disabled"></div>
                    </div>
                </div>

                <div class="cookie-buttons">
                    <button class="cookie-btn cookie-btn-primary" onclick="acceptAllCookies()">Alle akzeptieren</button>
                    <button class="cookie-btn cookie-btn-secondary" onclick="rejectAllCookies()">Alle ablehnen</button>
                    <button class="cookie-btn cookie-btn-tertiary" onclick="acceptSelectedCookies()">Nur Auswahl akzeptieren</button>
                </div>
            </div>
        </div>
    </div>

    <!-- Navigation -->
    <nav>
        <div class="container">
            <a href="#home" class="logo-link" onclick="hideLegalPage()" style="text-decoration: none;">
                <img src="logo.jpg" alt="Jashari Reinigungsservice Logo" class="logo-img">
            </a>
            <ul>
                <li><a href="#home">Start</a></li>
                <li><a href="#services">Dienstleistungen</a></li>
                <li><a href="#gallery">Galerie</a></li>
                <li><a href="#about">Über uns</a></li>
                <li><a href="#testimonials">Bewertungen</a></li>
                <li><a href="#contact">Kontakt</a></li>
            </ul>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>ReinigungsService Jashari</h1>
            <p class="tagline">„Wir reinigen gründlich, zuverlässig und mit Herz."</p>
            <div class="cta-buttons">
                <a href="tel:+4916363212685" class="btn btn-primary">📞 Jetzt anrufen</a>
                <a href="#contact" class="btn btn-secondary">📧 Angebot anfragen</a>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="services">
        <div class="container">
            <h2 class="section-title">Unsere Dienstleistungen</h2>
            <p class="section-subtitle">Professionelle Reinigungslösungen für jeden Bedarf</p>
            <div class="services-grid">
                <div class="service-card">
                    <div class="service-icon">🏢</div>
                    <h3>Büroreinigung</h3>
                    <p>Professionelle Reinigung Ihrer Geschäftsräume für ein sauberes und produktives Arbeitsumfeld. Flexibel nach Ihren Anforderungen – täglich, wöchentlich oder monatlich.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">🏠</div>
                    <h3>Haushaltsreinigung</h3>
                    <p>Gründliche Reinigung Ihres Zuhauses, damit Sie mehr Zeit für die wichtigen Dinge im Leben haben. Wir kümmern uns um alles – von Küche bis Badezimmer.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">✨</div>
                    <h3>Grundreinigung</h3>
                    <p>Intensive Tiefenreinigung für Neueinzug, Auszug oder einfach für einen kompletten Neustart Ihrer Räumlichkeiten. Wir erreichen auch schwer zugängliche Stellen.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">🪟</div>
                    <h3>Fensterreinigung</h3>
                    <p>Streifenfreie, kristallklare Fenster für optimalen Lichteinfall und perfekte Aussicht. Auch für schwer erreichbare Fenster und Fassaden.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">🏗️</div>
                    <h3>Baureinigung</h3>
                    <p>Professionelle Endreinigung nach Bau- oder Renovierungsarbeiten. Wir entfernen Baustaub, Farbreste und hinterlassen alles blitzsauber.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">🏥</div>
                    <h3>Praxisreinigung</h3>
                    <p>Hygienische Reinigung für Arztpraxen, Kanzleien und andere sensible Bereiche nach höchsten Standards. Diskretion garantiert.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Gallery Section -->
    <section id="gallery" class="gallery">
        <div class="container">
            <h2 class="section-title">Unsere Arbeit</h2>
            <p class="section-subtitle">Einblicke in unsere professionelle Reinigungsarbeit</p>
            <div class="gallery-grid">
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1527515637462-cff94eecc1ac?w=800&q=80" alt="Büroreinigung">
                    <div class="gallery-overlay">
                        <h3>Büroreinigung</h3>
                        <p>Saubere Arbeitsplätze für produktive Teams</p>
                    </div>
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1585421514738-01798e348b17?w=800&q=80" alt="Fensterreinigung">
                    <div class="gallery-overlay">
                        <h3>Fensterreinigung</h3>
                        <p>Kristallklare Fenster ohne Streifen</p>
                    </div>
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1584622650111-993a426fbf0a?w=800&q=80" alt="Haushaltsreinigung">
                    <div class="gallery-overlay">
                        <h3>Haushaltsreinigung</h3>
                        <p>Ihr Zuhause in besten Händen</p>
                    </div>
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1563453392212-326f5e854473?w=800&q=80" alt="Küche">
                    <div class="gallery-overlay">
                        <h3>Küchenreinigung</h3>
                        <p>Hygiene wo sie am wichtigsten ist</p>
                    </div>
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1600585152915-d208bec867a1?w=800&q=80" alt="Bad">
                    <div class="gallery-overlay">
                        <h3>Badreinigung</h3>
                        <p>Sanitäre Anlagen perfekt gereinigt</p>
                    </div>
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1600607687939-ce8a6c25118c?w=800&q=80" alt="Wohnzimmer">
                    <div class="gallery-overlay">
                        <h3>Wohnräume</h3>
                        <p>Gemütlichkeit trifft Sauberkeit</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <div class="container">
            <div class="about-content">
                <div class="about-text">
                    <h2 class="section-title">Warum ReinigungsService Jashari?</h2>
                    <p>Mit langjähriger Erfahrung und einem Team von qualifizierten, geschulten Fachkräften bieten wir professionelle Reinigungsdienstleistungen in Gelsenkirchen und der gesamten Umgebung an.</p>
                    <p>Unser Anspruch ist es, nicht nur sauber zu machen, sondern Ihre Räume zum Strahlen zu bringen. Mit modernsten Reinigungsmethoden, umweltfreundlichen Produkten und einem Auge fürs Detail sorgen wir dafür, dass Sie sich in Ihren Räumen rundum wohlfühlen.</p>
                    <p>Ihre Zufriedenheit ist unser Erfolg – deshalb arbeiten wir jeden Tag mit Leidenschaft und Herzblut.</p>
                </div>
                <div class="about-features">
                    <div class="feature-item">
                        <div class="feature-icon">✓</div>
                        <div>
                            <h3>Zuverlässigkeit</h3>
                            <p>Pünktlich, verlässlich und immer für Sie da. Wir halten unsere Termine ein und stehen zu unserem Wort.</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <div class="feature-icon">✓</div>
                        <div>
                            <h3>Höchste Qualität</h3>
                            <p>Perfektionistische Standards bei jedem Auftrag. Wir arbeiten nicht nach Checkliste, sondern nach Ergebnis.</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <div class="feature-icon">✓</div>
                        <div>
                            <h3>Faire Preise</h3>
                            <p>Transparente Kostenstruktur ohne versteckte Gebühren. Sie wissen immer genau, wofür Sie bezahlen.</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <div class="feature-icon">✓</div>
                        <div>
                            <h3>Umweltfreundlich</h3>
                            <p>Einsatz ökologischer Reinigungsmittel für Ihre Gesundheit und unsere Umwelt.</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section id="testimonials" class="testimonials">
        <div class="container">
            <h2 class="section-title">Was unsere Kunden sagen</h2>
            <p class="section-subtitle">Echte Bewertungen von zufriedenen Kunden</p>
            <div class="testimonials-grid">
                <div class="testimonial-card">
                    <div class="stars">★★★★★</div>
                    <p class="testimonial-text">"Absolut professioneller Service! Das Team war pünktlich, gründlich und sehr freundlich. Unser Büro war noch nie so sauber. Wir haben einen langfristigen Vertrag abgeschlossen und sind mehr als zufrieden!"</p>
                    <div class="testimonial-author">
                        <div class="author-avatar">MS</div>
                        <div class="author-info">
                            <h4>Michael Schmidt</h4>
                            <p>Geschäftsführer, Tech GmbH</p>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card">
                    <div class="stars">★★★★★</div>
                    <p class="testimonial-text">"Nach unserem Umzug haben wir ReinigungsService Jashari für die Grundreinigung beauftragt. Das Ergebnis hat unsere Erwartungen übertroffen! Jede Ecke war blitzsauber. Absolut empfehlenswert!"</p>
                    <div class="testimonial-author">
                        <div class="author-avatar">SK</div>
                        <div class="author-info">
                            <h4>Sarah Klein</h4>
                            <p>Privatkundin, Gelsenkirchen</p>
                        </div>
                    </div>
                </div>
                <div class="testimonial-card">
                    <div class="stars">★★★★★</div>
                    <p class="testimonial-text">"Zuverlässig, sauber, freundlich – was will man mehr? Die regelmäßige Reinigung unserer Praxis klappt einwandfrei. Das Team arbeitet diskret und professionell. Vielen Dank für die tolle Arbeit!"</p>
                    <div class="testimonial-author">
                        <div class="author-avatar">DM</div>
                        <div class="author-info">
                            <h4>Dr. med. Müller</h4>
                            <p>Arztpraxis, Essen</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <div class="container">
            <h2 class="section-title">Kontaktieren Sie uns</h2>
            <p class="section-subtitle">Wir freuen uns auf Ihre Anfrage!</p>
            <div class="contact-grid">
                <div class="contact-info">
                    <div class="contact-item">
                        <div class="contact-icon">📞</div>
                        <div>
                            <h3>Telefon</h3>
                            <a href="tel:+4916363212685">+49 163 6321268</a>
                            <p>Montag - Freitag: 8:00 - 18:00 Uhr<br>Samstag: 9:00 - 14:00 Uhr<br>Sonntag: Nach Vereinbarung</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">📧</div>
                        <div>
                            <h3>E-Mail</h3>
                            <a href="mailto:samimjasari@gmail.com">samimjasari@gmail.com</a>
                            <p>Wir antworten innerhalb von 24 Stunden</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">📍</div>
                        <div>
                            <h3>Einsatzgebiet</h3>
                            <p><strong>Gelsenkirchen und Umgebung</strong><br>
                        </div>
                    </div>
                </div>

                <div class="contact-form">
                    <h3 style="margin-bottom: 1.5rem; color: #1e293b; font-size: 1.5rem;">Kostenloses Angebot anfragen</h3>
                    <form action="mailto:samimjasari@gmail.com" method="POST" enctype="text/plain">
                        <div class="form-group">
                            <label for="name">Ihr Name *</label>
                            <input type="text" id="name" name="name" required placeholder="Max Mustermann">
                        </div>
                        <div class="form-group">
                            <label for="email">E-Mail Adresse *</label>
                            <input type="email" id="email" name="email" required placeholder="ihre@email.de">
                        </div>
                        <div class="form-group">
                            <label for="phone">Telefonnummer</label>
                            <input type="tel" id="phone" name="phone" placeholder="+49 123 456789">
                        </div>
                        <div class="form-group">
                            <label for="message">Ihre Nachricht *</label>
                            <textarea id="message" name="message" required placeholder="Beschreiben Sie bitte Ihr Anliegen... Welche Art von Reinigung benötigen Sie? Wie groß ist die Fläche?"></textarea>
                        </div>
                        <button type="submit" class="btn btn-primary" style="width: 100%;">📧 Nachricht senden</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Impressum Page -->
    <section id="impressum" class="legal-page">
        <div class="container">
            <div class="legal-content">
                <a href="#home" class="back-link" onclick="hideLegalPage()">← Zurück zur Startseite</a>
                <h1>Impressum</h1>
                
                <h2>Angaben gemäß § 5 TMG</h2>
                <p>
                    <strong>ReinigungsService Jashari</strong><br>
                    Inhaber: Samim Jashari<br>
                    Gelsenkirchen, Deutschland
                </p>

                <h2>Kontakt</h2>
                <p>
                    Telefon: <a href="tel:+4916363212685">+49 163 6321268</a><br>
                    E-Mail: <a href="mailto:samimjasari@gmail.com">samimjasari@gmail.com</a>
                </p>
                </p>

                <h2>Berufsbezeichnung und berufsrechtliche Regelungen</h2>
                <p>
                    Berufsbezeichnung: Reinigungsdienstleistungen<br>
                    Zuständige Kammer: Handwerkskammer Münster <br>
                    Betriebsnummer: 42069019 <br>
                    Verliehen in: Deutschland
                </p>

                <h2>Verbraucherstreitbeilegung / Universalschlichtungsstelle</h2>
                <p>
                    Wir sind nicht bereit oder verpflichtet, an Streitbeilegungsverfahren vor einer Verbraucherschlichtungsstelle teilzunehmen.
                </p>

                <h2>Haftung für Inhalte</h2>
                <p>
                    Als Diensteanbieter sind wir gemäß § 7 Abs.1 TMG für eigene Inhalte auf diesen Seiten nach den allgemeinen Gesetzen verantwortlich. Nach §§ 8 bis 10 TMG sind wir als Diensteanbieter jedoch nicht verpflichtet, übermittelte oder gespeicherte fremde Informationen zu überwachen oder nach Umständen zu forschen, die auf eine rechtswidrige Tätigkeit hinweisen.
                </p>
                <p>
                    Verpflichtungen zur Entfernung oder Sperrung der Nutzung von Informationen nach den allgemeinen Gesetzen bleiben hiervon unberührt. Eine diesbezügliche Haftung ist jedoch erst ab dem Zeitpunkt der Kenntnis einer konkreten Rechtsverletzung möglich. Bei Bekanntwerden von entsprechenden Rechtsverletzungen werden wir diese Inhalte umgehend entfernen.
                </p>

                <h2>Haftung für Links</h2>
                <p>
                    Unser Angebot enthält Links zu externen Websites Dritter, auf deren Inhalte wir keinen Einfluss haben. Deshalb können wir für diese fremden Inhalte auch keine Gewähr übernehmen. Für die Inhalte der verlinkten Seiten ist stets der jeweilige Anbieter oder Betreiber der Seiten verantwortlich. Die verlinkten Seiten wurden zum Zeitpunkt der Verlinkung auf mögliche Rechtsverstöße überprüft. Rechtswidrige Inhalte waren zum Zeitpunkt der Verlinkung nicht erkennbar.
                </p>

                <h2>Urheberrecht</h2>
                <p>
                    Die durch die Seitenbetreiber erstellten Inhalte und Werke auf diesen Seiten unterliegen dem deutschen Urheberrecht. Die Vervielfältigung, Bearbeitung, Verbreitung und jede Art der Verwertung außerhalb der Grenzen des Urheberrechtes bedürfen der schriftlichen Zustimmung des jeweiligen Autors bzw. Erstellers. Downloads und Kopien dieser Seite sind nur für den privaten, nicht kommerziellen Gebrauch gestattet.
                </p>
            </div>
        </div>
    </section>

    <!-- AGB Page -->
    <section id="agb" class="legal-page">
        <div class="container">
            <div class="legal-content">
                <a href="#home" class="back-link" onclick="hideLegalPage()">← Zurück zur Startseite</a>
                <h1>Allgemeine Geschäftsbedingungen (AGB)</h1>
                
                <h2>1. Geltungsbereich</h2>
                <p>
                    Diese Allgemeinen Geschäftsbedingungen gelten für alle Verträge zwischen ReinigungsService Jashari (nachfolgend "Auftragnehmer") und dem Kunden (nachfolgend "Auftraggeber") über die Erbringung von Reinigungsdienstleistungen.
                </p>

                <h2>2. Vertragsschluss</h2>
                <p>
                    Der Vertrag kommt durch die Auftragsbestätigung des Auftragnehmers zustande. Mündliche Nebenabreden bedürfen zu ihrer Wirksamkeit der Schriftform. Änderungen und Ergänzungen des Vertrages sind nur wirksam, wenn sie schriftlich vereinbart werden.
                </p>

                <h2>3. Leistungsumfang</h2>
                <p>
                    Der Umfang der zu erbringenden Reinigungsleistungen ergibt sich aus der Auftragsbestätigung und den darin aufgeführten Leistungsbeschreibungen. Zusätzliche Leistungen werden gesondert berechnet.
                </p>

                <h2>4. Ausführung der Arbeiten</h2>
                <p>
                    <strong>4.1</strong> Die vereinbarten Reinigungsarbeiten werden zu den vereinbarten Zeiten durchgeführt. Bei Verhinderung hat der Auftraggeber den Auftragnehmer rechtzeitig zu informieren.
                </p>
                <p>
                    <strong>4.2</strong> Der Auftraggeber stellt dem Auftragnehmer alle notwendigen Zugänge zu den zu reinigenden Räumlichkeiten zur Verfügung. Dies umfasst auch die Bereitstellung von Strom- und Wasseranschlüssen.
                </p>
                <p>
                    <strong>4.3</strong> Der Auftragnehmer ist berechtigt, Unterauftragnehmer einzusetzen.
                </p>

                <h2>5. Preise und Zahlungsbedingungen</h2>
                <p>
                    <strong>5.1</strong> Es gelten die im Angebot bzw. in der Auftragsbestätigung genannten Preise. Alle Preise verstehen sich inklusive der gesetzlichen Mehrwertsteuer.
                </p>
                <p>
                    <strong>5.2</strong> Die Rechnungsstellung erfolgt nach Leistungserbringung. Der Rechnungsbetrag ist innerhalb von 14 Tagen nach Rechnungsdatum ohne Abzug zur Zahlung fällig.
                </p>
                <p>
                    <strong>5.3</strong> Bei Zahlungsverzug werden Verzugszinsen in Höhe von 5 Prozentpunkten über dem Basiszinssatz berechnet.
                </p>

                <h2>6. Termine und Fristen</h2>
                <p>
                    Termine und Fristen werden nach Möglichkeit eingehalten. Der Auftragnehmer haftet jedoch nur bei Vorsatz oder grober Fahrlässigkeit für die Nichteinhaltung von Terminen und Fristen.
                </p>

                <h2>7. Pflichten des Auftraggebers</h2>
                <p>
                    <strong>7.1</strong> Der Auftraggeber hat dafür Sorge zu tragen, dass die zu reinigenden Räumlichkeiten zugänglich sind und die erforderlichen Anschlüsse zur Verfügung stehen.
                </p>
                <p>
                    <strong>7.2</strong> Wertgegenstände, Bargeld, Schmuck und andere wertvollen Gegenstände sind vom Auftraggeber in Sicherheit zu bringen.
                </p>
                <p>
                    <strong>7.3</strong> Der Auftraggeber hat den Auftragnehmer auf besondere Gefahrenquellen oder empfindliche Gegenstände hinzuweisen.
                </p>

                <h2>8. Haftung</h2>
                <p>
                    <strong>8.1</strong> Der Auftragnehmer haftet für Schäden nur bei Vorsatz und grober Fahrlässigkeit. Die Haftung für leichte Fahrlässigkeit ist ausgeschlossen.
                </p>
                <p>
                    <strong>8.2</strong> Reklamationen sind unverzüglich, spätestens jedoch innerhalb von 24 Stunden nach Leistungserbringung, schriftlich anzuzeigen.
                </p>
                <p>
                    <strong>8.3</strong> Die Haftung ist auf den typischerweise vorhersehbaren Schaden begrenzt.
                </p>

                <h2>9. Kündigung</h2>
                <p>
                    <strong>9.1</strong> Einzelaufträge können bis 48 Stunden vor dem vereinbarten Termin kostenfrei storniert werden. Bei späterer Stornierung werden 50% der vereinbarten Vergütung berechnet.
                </p>
                <p>
                    <strong>9.2</strong> Dauerschuldverhältnisse können von beiden Parteien mit einer Frist von 4 Wochen zum Monatsende gekündigt werden.
                </p>
                <p>
                    <strong>9.3</strong> Das Recht zur außerordentlichen Kündigung aus wichtigem Grund bleibt unberührt.
                </p>

                <h2>10. Datenschutz</h2>
                <p>
                    Der Auftragnehmer behandelt alle im Rahmen der Geschäftsbeziehung bekannt gewordenen Daten vertraulich und entsprechend der geltenden Datenschutzbestimmungen.
                </p>

                <h2>11. Schlussbestimmungen</h2>
                <p>
                    <strong>11.1</strong> Es gilt das Recht der Bundesrepublik Deutschland.
                </p>
                <p>
                    <strong>11.2</strong> Gerichtsstand ist, soweit gesetzlich zulässig, der Sitz des Auftragnehmers.
                </p>
                <p>
                    <strong>11.3</strong> Sollten einzelne Bestimmungen dieser AGB unwirksam sein oder werden, wird die Wirksamkeit der übrigen Bestimmungen davon nicht berührt.
                </p>

                <p style="margin-top: 3rem;">
                    <strong>Stand:</strong> November 2025<br>
                    <strong>ReinigungsService Jashari</strong>
                </p>
            </div>
        </div>
    </section>

    <!-- Datenschutz Page -->
    <section id="datenschutz" class="legal-page">
        <div class="container">
            <div class="legal-content">
                <a href="#home" class="back-link" onclick="hideLegalPage()">← Zurück zur Startseite</a>
                <h1>Datenschutzerklärung</h1>
                
                <h2>1. Datenschutz auf einen Blick</h2>
                <h3>Allgemeine Hinweise</h3>
                <p>
                    Die folgenden Hinweise geben einen einfachen Überblick darüber, was mit Ihren personenbezogenen Daten passiert, wenn Sie diese Website besuchen. Personenbezogene Daten sind alle Daten, mit denen Sie persönlich identifiziert werden können.
                </p>

                <h3>Datenerfassung auf dieser Website</h3>
                <p>
                    <strong>Wer ist verantwortlich für die Datenerfassung auf dieser Website?</strong><br>
                    Die Datenverarbeitung auf dieser Website erfolgt durch den Websitebetreiber. Dessen Kontaktdaten können Sie dem Impressum dieser Website entnehmen.
                </p>

                <h2>2. Hosting</h2>
                <p>
                    Diese Website wird extern gehostet. Die personenbezogenen Daten, die auf dieser Website erfasst werden, werden auf den Servern des Hosters gespeichert. Hierbei kann es sich v. a. um IP-Adressen, Kontaktanfragen, Meta- und Kommunikationsdaten, Vertragsdaten, Kontaktdaten, Namen, Websitezugriffe und sonstige Daten, die über eine Website generiert werden, handeln.
                </p>

                <h2>3. Allgemeine Hinweise und Pflichtinformationen</h2>
                <h3>Datenschutz</h3>
                <p>
                    Die Betreiber dieser Seiten nehmen den Schutz Ihrer persönlichen Daten sehr ernst. Wir behandeln Ihre personenbezogenen Daten vertraulich und entsprechend der gesetzlichen Datenschutzvorschriften sowie dieser Datenschutzerklärung.
                </p>

                <h3>Hinweis zur verantwortlichen Stelle</h3>
                <p>
                    Die verantwortliche Stelle für die Datenverarbeitung auf dieser Website ist:<br><br>
                    <strong>ReinigungsService Jashari</strong><br>
                    Inhaber: Samim Jashari<br>
                    Telefon: +49 163 6321268<br>
                    E-Mail: <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="6f1c0e020602050e1c0e1d062f08020e0603410c0002">[email&#160;protected]</a>
                </p>

                <h3>Speicherdauer</h3>
                <p>
                    Soweit innerhalb dieser Datenschutzerklärung keine speziellere Speicherdauer genannt wurde, verbleiben Ihre personenbezogenen Daten bei uns, bis der Zweck für die Datenverarbeitung entfällt.
                </p>

                <h3>Ihre Rechte</h3>
                <p>
                    Sie haben jederzeit das Recht unentgeltlich Auskunft über Herkunft, Empfänger und Zweck Ihrer gespeicherten personenbezogenen Daten zu erhalten. Sie haben außerdem ein Recht, die Berichtigung oder Löschung dieser Daten zu verlangen.
                </p>

                <h2>4. Datenerfassung auf dieser Website</h2>
                <h3>Kontaktformular</h3>
                <p>
                    Wenn Sie uns per Kontaktformular Anfragen zukommen lassen, werden Ihre Angaben aus dem Anfrageformular inklusive der von Ihnen dort angegebenen Kontaktdaten zwecks Bearbeitung der Anfrage und für den Fall von Anschlussfragen bei uns gespeichert.
                </p>

                <h3>Anfrage per E-Mail oder Telefon</h3>
                <p>
                    Wenn Sie uns per E-Mail oder Telefon kontaktieren, wird Ihre Anfrage inklusive aller daraus hervorgehenden personenbezogenen Daten (Name, Anfrage) zum Zwecke der Bearbeitung Ihres Anliegens bei uns gespeichert und verarbeitet.
                </p>

                <h2>5. Cookies</h2>
                <p>
                    Diese Website verwendet nur technisch notwendige Cookies. Diese Cookies sind erforderlich, um die grundlegenden Funktionen der Website zu gewährleisten. Dabei handelt es sich um Cookies, die für den Betrieb der Seite zwingend erforderlich sind.
                </p>

                <p style="margin-top: 3rem;">
                    <strong>Stand:</strong> November 2025<br>
                    <strong>ReinigungsService Jashari</strong>
                </p>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>ReinigungsService Jashari</h3>
                    <p>Ihr zuverlässiger Partner für professionelle Reinigungsdienstleistungen in Gelsenkirchen und Umgebung.</p>
                    <p style="margin-top: 1rem;">„Wir reinigen gründlich, zuverlässig und mit Herz."</p>
                </div>
                <div class="footer-section">
                    <h3>Schnellkontakt</h3>
                    <p>📞 <a href="tel:+4916363212685">+49 163 6321268</a></p>
                    <p>📧 <a href="mailto:samimjasari@gmail.com">samimjasari@gmail.com</a></p>
                    <p>📍 Gelsenkirchen & Umgebung</p>
                </div>
                <div class="footer-section">
                    <h3>Öffnungszeiten</h3>
                    <p>Montag - Freitag: 8:00 - 18:00 Uhr</p>
                    <p>Samstag: 9:00 - 14:00 Uhr</p>
                    <p>Sonntag: Nach Vereinbarung</p>
                </div>
                <div class="footer-section">
                    <h3>Rechtliches</h3>
                    <div class="footer-links">
                        <a href="#impressum" onclick="showLegalPage('impressum')">Impressum</a>
                        <a href="#agb" onclick="showLegalPage('agb')">AGB</a>
                        <a href="#datenschutz" onclick="showLegalPage('datenschutz')">Datenschutz</a>
                        <a href="#" onclick="showCookieSettings(); return false;">Cookie-Einstellungen</a>
                    </div>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2025 ReinigungsService Jashari. Alle Rechte vorbehalten.</p>
                <div class="footer-legal-links">
                    <a href="#impressum" onclick="showLegalPage('impressum')">Impressum</a>
                    <a href="#agb" onclick="showLegalPage('agb')">AGB</a>
                    <a href="#datenschutz" onclick="showLegalPage('datenschutz')">Datenschutz</a>
                    <a href="#" onclick="showCookieSettings(); return false;">Cookie-Einstellungen</a>
                </div>
            </div>
        </div>
    </footer>

    <!-- Scroll to top button -->
    <div class="scroll-top" onclick="window.scrollTo({top: 0, behavior: 'smooth'})">↑</div>

    <script data-cfasync="false" src="/cdn-cgi/scripts/5c5dd728/cloudflare-static/email-decode.min.js"></script><script>
        // Cookie Management
        function getCookie(name) {
            const value = `; ${document.cookie}`;
            const parts = value.split(`; ${name}=`);
            if (parts.length === 2) return parts.pop().split(';').shift();
        }

        function setCookie(name, value, days) {
            const expires = new Date(Date.now() + days * 864e5).toUTCString();
            document.cookie = `${name}=${value}; expires=${expires}; path=/`;
        }

        function checkCookieConsent() {
            const consent = getCookie('cookie_consent');
            if (!consent) {
                document.getElementById('cookieBanner').classList.remove('hidden');
            }
        }

        function closeCookieBanner() {
            document.getElementById('cookieBanner').classList.add('hidden');
        }

        function acceptAllCookies() {
            setCookie('cookie_consent', 'all', 365);
            closeCookieBanner();
        }

        function rejectAllCookies() {
            setCookie('cookie_consent', 'necessary', 365);
            closeCookieBanner();
        }

        function acceptSelectedCookies() {
            setCookie('cookie_consent', 'necessary', 365);
            closeCookieBanner();
        }

        function showCookieSettings() {
            document.getElementById('cookieBanner').classList.remove('hidden');
        }

        // Check cookie consent on page load
        window.addEventListener('load', checkCookieConsent);

        // Show/hide scroll to top button
        window.addEventListener('scroll', function() {
            const scrollTop = document.querySelector('.scroll-top');
            if (window.scrollY > 500) {
                scrollTop.classList.add('visible');
            } else {
                scrollTop.classList.remove('visible');
            }
        });

        // Smooth scroll for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                const href = this.getAttribute('href');
                // Don't prevent default for legal pages
                if (href === '#impressum' || href === '#agb' || href === '#datenschutz') {
                    return;
                }
                
                e.preventDefault();
                const target = document.querySelector(href);
                if (target && !target.classList.contains('legal-page')) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Legal pages navigation
        function showLegalPage(pageId, event) {
            if (event) event.preventDefault();
            document.body.classList.add('show-legal');
            
            // Hide all legal pages
            document.querySelectorAll('.legal-page').forEach(page => {
                page.style.display = 'none';
            });
            
            // Show selected legal page
            const targetPage = document.getElementById(pageId);
            if (targetPage) {
                targetPage.style.display = 'block';
                window.scrollTo({top: 0, behavior: 'smooth'});
            }
        }

        function hideLegalPage(event) {
            if (event) event.preventDefault();
              document.body.classList.remove('show-legal');
            
            // Hide all legal pages
            // Hide all legal pages
document.querySelectorAll('.legal-page').forEach(page => {
    page.style.display = 'none';
});

            
            window.scrollTo({top: 0, behavior: 'smooth'});
        }

        // Check URL hash on page load
        window.addEventListener('load', function() {
            const hash = window.location.hash.substring(1);
            if (hash === 'impressum' || hash === 'agb' || hash === 'datenschutz') {
                showLegalPage(hash);
            }
        });
    </script>
</body>
</html>



<img width="1500" height="574" alt="image" src="https://github.com/user-attachments/assets/30d663cd-377a-403e-8a5e-f7cc781e155e" />
<img width="16" height="16" alt="image" src="https://github.com/user-attachments/assets/414a9808-c13c-485a-8c22-1ac35e10c5a6" />

