<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gastronomía del Cantón Salitre - Sabores Auténticos</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&family=Poppins:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --color-primary: #8B4513;
            --color-secondary: #F5DEB3;
            --color-accent: #A52A2A;
            --color-light: #FFF8DC;
            --color-dark: #3C2A1E;
            --color-white: #FFFFFF;
            --color-gold: #D4AF37;
            --shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            --shadow-hover: 0 15px 30px rgba(0, 0, 0, 0.2);
            --transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            --border-radius: 12px;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Poppins', sans-serif;
            color: var(--color-dark);
            background-color: var(--color-white);
            line-height: 1.6;
            overflow-x: hidden;
            position: relative;
        }

        /* Fondo elegante sutil */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 80%, rgba(139, 69, 19, 0.03) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(165, 42, 42, 0.03) 0%, transparent 50%);
            z-index: -1;
            pointer-events: none;
            animation: gradientFloat 20s ease infinite;
        }

        h1, h2, h3, h4 {
            font-family: 'Playfair Display', serif;
            font-weight: 700;
            margin-bottom: 1.5rem;
            color: var(--color-primary);
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
        }

        /* Header y Navegación - ORIGINAL */
        header {
            background: linear-gradient(to right, rgba(139, 69, 19, 0.9), rgba(165, 42, 42, 0.8));
            color: var(--color-white);
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        header.scrolled {
            padding: 0.7rem 0;
            background: rgba(139, 69, 19, 0.98);
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            animation: fadeIn 1.5s ease;
        }

        .logo h1 {
            font-size: 1.8rem;
            margin: 0;
            color: var(--color-white);
        }

        .logo span {
            color: var(--color-secondary);
        }

        nav ul {
            display: flex;
            list-style: none;
        }

        nav ul li {
            margin-left: 2rem;
        }

        nav ul li a {
            color: var(--color-white);
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
            position: relative;
            padding: 0.5rem 0;
        }

        nav ul li a:after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: 0;
            left: 0;
            background-color: var(--color-secondary);
            transition: var(--transition);
        }

        nav ul li a:hover:after {
            width: 100%;
        }

        /* Hero Section - EXACTAMENTE IGUAL */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('https://images.unsplash.com/photo-1504674900247-0877df9cc836?ixlib=rb-4.0.3&auto=format&fit=crop&w=1350&q=80') no-repeat center center/cover;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: var(--color-white);
            padding-top: 80px;
        }

        .hero-content {
            max-width: 800px;
            animation: slideUp 1.5s ease;
        }

        .hero h2 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            color: var(--color-white);
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
        }

        .btn {
            display: inline-block;
            background: var(--color-primary);
            color: var(--color-white);
            padding: 0.8rem 1.8rem;
            border: none;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
            cursor: pointer;
            box-shadow: var(--shadow);
        }

        .btn:hover {
            background: var(--color-accent);
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }

        /* Secciones */
        section {
            padding: 5rem 0;
            position: relative;
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
        }

        .section-title h2 {
            font-size: 2.5rem;
            display: inline-block;
            position: relative;
        }

        .section-title h2:after {
            content: '';
            position: absolute;
            width: 60%;
            height: 3px;
            background: var(--color-primary);
            bottom: -10px;
            left: 20%;
            animation: lineExpand 2s ease-out;
        }

        /* PLATILLOS MEJORADOS */
        .dishes {
            background-color: var(--color-light);
        }

        .dishes-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2.5rem;
        }

        .dish-card {
            background: var(--color-white);
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            animation: cardFloat 0.8s ease-out;
            position: relative;
            cursor: pointer;
        }

        .dish-card:hover {
            transform: translateY(-15px) scale(1.02);
            box-shadow: var(--shadow-hover);
        }

        .dish-img {
            height: 250px;
            overflow: hidden;
            position: relative;
        }

        .dish-img::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 50%;
            background: linear-gradient(to top, rgba(0,0,0,0.7), transparent);
            opacity: 0;
            transition: var(--transition);
        }

        .dish-card:hover .dish-img::after {
            opacity: 1;
        }

        .dish-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.8s ease;
        }

        .dish-card:hover .dish-img img {
            transform: scale(1.15);
        }

        .dish-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(139, 69, 19, 0.9);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: var(--transition);
            padding: 2rem;
            text-align: center;
            color: var(--color-white);
        }

        .dish-card:hover .dish-overlay {
            opacity: 1;
        }

        .dish-overlay h4 {
            color: var(--color-gold);
            margin-bottom: 1rem;
            font-size: 1.5rem;
        }

        .dish-overlay p {
            font-size: 0.95rem;
            margin-bottom: 1.5rem;
            opacity: 0.9;
        }

        .view-details {
            background: var(--color-gold);
            color: var(--color-dark);
            border: none;
            padding: 0.8rem 1.5rem;
            border-radius: 25px;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .view-details:hover {
            background: var(--color-white);
            transform: translateY(-3px);
        }

        .dish-info {
            padding: 1.8rem;
        }

        .dish-info h3 {
            font-size: 1.6rem;
            margin-bottom: 0.8rem;
            color: var(--color-primary);
        }

        .dish-info p {
            color: #666;
            margin-bottom: 1.2rem;
            font-size: 0.95rem;
        }

        .dish-meta {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 1rem;
            padding-top: 1rem;
            border-top: 1px solid rgba(0,0,0,0.1);
        }

        .dish-origin {
            display: flex;
            align-items: center;
            gap: 5px;
            color: var(--color-accent);
            font-size: 0.9rem;
        }

        .dish-origin i {
            font-size: 1rem;
        }

        .dish-link {
            color: var(--color-primary);
            text-decoration: none;
            font-weight: 600;
            font-size: 0.9rem;
            display: flex;
            align-items: center;
            gap: 5px;
            transition: var(--transition);
        }

        .dish-link:hover {
            color: var(--color-accent);
            gap: 8px;
        }

        /* MODALES PROFESIONALES */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.85);
            z-index: 2000;
            justify-content: center;
            align-items: center;
            padding: 20px;
            animation: modalFadeIn 0.3s ease;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background: var(--color-white);
            border-radius: var(--border-radius);
            max-width: 800px;
            width: 100%;
            max-height: 90vh;
            overflow-y: auto;
            position: relative;
            animation: modalSlideUp 0.5s ease;
            box-shadow: 0 25px 50px rgba(0,0,0,0.5);
        }

        .modal-header {
            padding: 2rem 2rem 1rem;
            border-bottom: 1px solid rgba(0,0,0,0.1);
            position: relative;
        }

        .modal-header h3 {
            font-size: 2.2rem;
            color: var(--color-primary);
            margin-bottom: 0.5rem;
        }

        .modal-subtitle {
            color: var(--color-accent);
            font-style: italic;
            margin-bottom: 1rem;
        }

        .modal-close {
            position: absolute;
            top: 1.5rem;
            right: 1.5rem;
            background: var(--color-primary);
            color: var(--color-white);
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: var(--transition);
            border: none;
            font-size: 1.2rem;
        }

        .modal-close:hover {
            background: var(--color-accent);
            transform: rotate(90deg);
        }

        .modal-body {
            padding: 2rem;
        }

        .modal-image {
            width: 100%;
            height: 300px;
            border-radius: 10px;
            overflow: hidden;
            margin-bottom: 2rem;
        }

        .modal-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .modal-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .modal-info h4 {
            color: var(--color-primary);
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }

        .ingredients-list {
            list-style: none;
        }

        .ingredients-list li {
            padding: 0.5rem 0;
            border-bottom: 1px dashed rgba(0,0,0,0.1);
            display: flex;
            justify-content: space-between;
        }

        .ingredients-list li:last-child {
            border-bottom: none;
        }

        .ingredient-name {
            font-weight: 500;
        }

        .ingredient-origin {
            color: var(--color-accent);
            font-size: 0.9rem;
        }

        .modal-footer {
            padding: 1.5rem 2rem;
            background: var(--color-light);
            border-top: 1px solid rgba(0,0,0,0.1);
            text-align: center;
        }

        /* INGREDIENTES MEJORADOS */
        .ingredients {
            background: linear-gradient(135deg, var(--color-primary) 0%, #A0522D 100%);
            color: var(--color-white);
            position: relative;
            overflow: hidden;
        }

        .ingredients::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
            animation: rotateSlow 30s linear infinite;
        }

        .ingredients h2 {
            color: var(--color-white);
            position: relative;
            z-index: 1;
        }

        .ingredients-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2.5rem;
            position: relative;
            z-index: 1;
        }

        .ingredient-card {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(15px);
            padding: 2.5rem;
            border-radius: var(--border-radius);
            text-align: center;
            transition: var(--transition);
            border: 1px solid rgba(255, 255, 255, 0.2);
            animation: cardFloat 1s ease-out;
            position: relative;
            overflow: hidden;
        }

        .ingredient-card:hover {
            transform: translateY(-15px) rotate(2deg);
            background: rgba(255, 255, 255, 0.25);
            border-color: var(--color-gold);
        }

        .ingredient-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(to right, var(--color-gold), var(--color-accent));
        }

        .ingredient-icon {
            font-size: 4rem;
            margin-bottom: 1.5rem;
            color: var(--color-gold);
            transition: var(--transition);
            filter: drop-shadow(0 2px 4px rgba(0,0,0,0.3));
        }

        .ingredient-card:hover .ingredient-icon {
            transform: scale(1.2) rotate(10deg);
        }

        .ingredient-card h3 {
            color: var(--color-white);
            margin-bottom: 1rem;
            font-size: 1.5rem;
        }

        .ingredient-card p {
            opacity: 0.9;
            font-size: 1rem;
        }

        /* RESTAURANTES MEJORADOS */
        .restaurants-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 3rem;
        }

        .restaurant-card {
            background: var(--color-white);
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            animation: cardFloat 0.8s ease-out;
            position: relative;
        }

        .restaurant-card:hover {
            transform: translateY(-15px);
            box-shadow: var(--shadow-hover);
        }

        .restaurant-img {
            height: 250px;
            overflow: hidden;
            position: relative;
        }

        .restaurant-img::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 50%;
            background: linear-gradient(to top, rgba(0,0,0,0.7), transparent);
        }

        .restaurant-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.8s ease;
        }

        .restaurant-card:hover .restaurant-img img {
            transform: scale(1.1);
        }

        .restaurant-badge {
            position: absolute;
            top: 20px;
            right: 20px;
            background: var(--color-gold);
            color: var(--color-dark);
            padding: 0.5rem 1.2rem;
            border-radius: 20px;
            font-weight: 700;
            font-size: 0.9rem;
            z-index: 2;
            box-shadow: var(--shadow);
        }

        .restaurant-info {
            padding: 2rem;
        }

        .restaurant-info h3 {
            font-size: 1.7rem;
            margin-bottom: 0.5rem;
            color: var(--color-primary);
        }

        .restaurant-rating {
            color: var(--color-gold);
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 5px;
        }

        .restaurant-features {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin: 1.5rem 0;
        }

        .feature {
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 0.9rem;
            color: var(--color-accent);
            background: rgba(139, 69, 19, 0.1);
            padding: 0.5rem 1rem;
            border-radius: 20px;
        }

        .feature i {
            font-size: 1rem;
            color: var(--color-primary);
        }

        .restaurant-link {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            color: var(--color-primary);
            text-decoration: none;
            font-weight: 600;
            margin-top: 1rem;
            padding: 0.8rem 1.5rem;
            background: rgba(139, 69, 19, 0.1);
            border-radius: 25px;
            transition: var(--transition);
        }

        .restaurant-link:hover {
            color: var(--color-white);
            background: var(--color-primary);
            gap: 15px;
            box-shadow: var(--shadow);
        }

        /* RECETAS MEJORADAS */
        .recipes {
            background-color: var(--color-light);
            position: relative;
            overflow: hidden;
        }

        .recipes::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml,<svg width="100" height="100" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg"><path d="M20,20 Q50,5 80,20 T100,50 T80,80 T50,95 T20,80 T0,50 T20,20 Z" fill="%238B4513" opacity="0.03"/></svg>');
            animation: patternMove 20s linear infinite;
        }

        .recipe-tabs {
            display: flex;
            justify-content: center;
            margin-bottom: 3rem;
            flex-wrap: wrap;
            gap: 1rem;
            position: relative;
            z-index: 1;
        }

        .recipe-tab {
            padding: 1rem 2rem;
            background: var(--color-white);
            border: 2px solid transparent;
            border-radius: 30px;
            cursor: pointer;
            transition: var(--transition);
            font-weight: 600;
            font-size: 1.1rem;
            box-shadow: var(--shadow);
            display: flex;
            align-items: center;
            gap: 10px;
            position: relative;
            overflow: hidden;
        }

        .recipe-tab::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(139, 69, 19, 0.1), transparent);
            transition: 0.6s;
        }

        .recipe-tab:hover::before {
            left: 100%;
        }

        .recipe-tab:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-hover);
            border-color: var(--color-primary);
        }

        .recipe-tab.active {
            background: var(--color-primary);
            color: var(--color-white);
            border-color: var(--color-primary);
        }

        .recipe-tab i {
            font-size: 1.2rem;
        }

        .recipe-content {
            display: none;
            animation: fadeInUp 0.8s ease;
            position: relative;
            z-index: 1;
            background: var(--color-white);
            padding: 3rem;
            border-radius: var(--border-radius);
            box-shadow: var(--shadow);
        }

        .recipe-content.active {
            display: block;
        }

        .recipe-details {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: start;
        }

        .recipe-ingredients {
            background: var(--color-light);
            padding: 2rem;
            border-radius: var(--border-radius);
        }

        .recipe-ingredients h4 {
            color: var(--color-primary);
            margin-bottom: 1.5rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .recipe-ingredients ul {
            list-style: none;
        }

        .recipe-ingredients li {
            padding: 0.8rem 0;
            border-bottom: 1px dashed rgba(0,0,0,0.1);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .recipe-ingredients li:last-child {
            border-bottom: none;
        }

        .recipe-ingredients li i {
            color: var(--color-gold);
        }

        .recipe-steps {
            padding: 2rem;
            background: var(--color-light);
            border-radius: var(--border-radius);
        }

        .recipe-steps h4 {
            color: var(--color-primary);
            margin-bottom: 1.5rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .recipe-step {
            margin-bottom: 1.5rem;
            padding-left: 2.5rem;
            position: relative;
            counter-increment: step;
        }

        .recipe-step::before {
            content: counter(step);
            position: absolute;
            left: 0;
            top: 0;
            background: var(--color-primary);
            color: var(--color-white);
            width: 35px;
            height: 35px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            box-shadow: var(--shadow);
        }

        /* CULTURA MEJORADA */
        .culture-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .culture-text {
            animation: slideLeft 1s ease;
            position: relative;
        }

        .culture-text p {
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
            position: relative;
            padding-left: 2rem;
            line-height: 1.8;
        }

        .culture-text p::before {
            content: '✦';
            position: absolute;
            left: 0;
            top: 0;
            color: var(--color-primary);
            font-size: 1.2rem;
        }

        .culture-gallery {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 1rem;
            animation: slideRight 1s ease;
        }

        .culture-img {
            border-radius: var(--border-radius);
            overflow: hidden;
            position: relative;
            cursor: pointer;
            height: 200px;
            transition: var(--transition);
        }

        .culture-img:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-hover);
        }

        .culture-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.6s ease;
        }

        .culture-img:hover img {
            transform: scale(1.2);
        }

        .culture-img::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(to top, rgba(0,0,0,0.5), transparent);
            opacity: 0;
            transition: var(--transition);
        }

        .culture-img:hover::after {
            opacity: 1;
        }

        /* FOOTER MEJORADO */
        footer {
            background: linear-gradient(135deg, var(--color-dark) 0%, #2C1810 100%);
            color: var(--color-white);
            padding: 4rem 0 2rem;
            position: relative;
            overflow: hidden;
        }

        footer::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: linear-gradient(to right, var(--color-primary), var(--color-gold), var(--color-accent));
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
            margin-bottom: 3rem;
            position: relative;
            z-index: 1;
        }

        .footer-section h3 {
            color: var(--color-gold);
            margin-bottom: 1.5rem;
            font-size: 1.5rem;
            position: relative;
            padding-bottom: 0.8rem;
        }

        .footer-section h3::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 40px;
            height: 3px;
            background: var(--color-primary);
            transition: var(--transition);
        }

        .footer-section:hover h3::after {
            width: 60px;
        }

        .footer-section p {
            margin-bottom: 1rem;
            color: rgba(255,255,255,0.8);
            line-height: 1.7;
        }

        .contact-info {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 1rem;
            transition: var(--transition);
        }

        .contact-info:hover {
            transform: translateX(10px);
        }

        .contact-info i {
            color: var(--color-gold);
            font-size: 1.1rem;
            width: 20px;
        }

        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1.5rem;
        }

        .social-links a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 45px;
            height: 45px;
            background: rgba(255, 255, 255, 0.1);
            color: var(--color-white);
            border-radius: 50%;
            transition: var(--transition);
            font-size: 1.2rem;
            position: relative;
            overflow: hidden;
        }

        .social-links a::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: 0.6s;
        }

        .social-links a:hover::before {
            left: 100%;
        }

        .social-links a:hover {
            background: var(--color-primary);
            transform: translateY(-5px) rotate(10deg);
            color: var(--color-gold);
        }

        .quick-links ul {
            list-style: none;
        }

        .quick-links ul li {
            margin-bottom: 0.8rem;
        }

        .quick-links ul li a {
            color: rgba(255,255,255,0.8);
            text-decoration: none;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 0.3rem 0;
        }

        .quick-links ul li a:hover {
            color: var(--color-gold);
            transform: translateX(10px);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: rgba(255,255,255,0.6);
            position: relative;
            z-index: 1;
        }

        /* ANIMACIONES PROFESIONALES */
        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes slideLeft {
            from {
                opacity: 0;
                transform: translateX(50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes slideRight {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes modalFadeIn {
            from {
                opacity: 0;
                backdrop-filter: blur(0);
            }
            to {
                opacity: 1;
                backdrop-filter: blur(5px);
            }
        }

        @keyframes modalSlideUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes pulse {
            0%, 100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.05);
            }
        }

        @keyframes gentlePulse {
            0%, 100% {
                transform: scale(1);
                box-shadow: 0 5px 20px rgba(37, 211, 102, 0.5);
            }
            50% {
                transform: scale(1.05);
                box-shadow: 0 5px 25px rgba(37, 211, 102, 0.7);
            }
        }

        @keyframes cardFloat {
            0% {
                opacity: 0;
                transform: translateY(30px) rotateX(10deg);
            }
            100% {
                opacity: 1;
                transform: translateY(0) rotateX(0);
            }
        }

        @keyframes lineExpand {
            0% {
                width: 0;
                opacity: 0;
            }
            100% {
                width: 60%;
                opacity: 1;
            }
        }

        @keyframes fadeInUp {
            0% {
                opacity: 0;
                transform: translateY(20px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes gradientFloat {
            0%, 100% {
                background-position: 0% 50%;
            }
            50% {
                background-position: 100% 50%;
            }
        }

        @keyframes rotateSlow {
            from {
                transform: rotate(0deg);
            }
            to {
                transform: rotate(360deg);
            }
        }

        @keyframes patternMove {
            0% {
                background-position: 0 0;
            }
            100% {
                background-position: 100px 100px;
            }
        }

        /* RESPONSIVE */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
            }

            nav ul {
                margin-top: 1rem;
                flex-wrap: wrap;
                justify-content: center;
            }

            nav ul li {
                margin: 0.5rem;
            }

            .hero h2 {
                font-size: 2.5rem;
            }

            .culture-content {
                grid-template-columns: 1fr;
            }

            .recipe-details {
                grid-template-columns: 1fr;
            }

            .dishes-grid,
            .restaurants-grid {
                grid-template-columns: 1fr;
            }

            .modal-content {
                width: 95%;
                max-height: 85vh;
            }
        }

        @media (max-width: 480px) {
            .hero h2 {
                font-size: 2rem;
            }

            .section-title h2 {
                font-size: 2rem;
            }

            .recipe-tabs {
                flex-direction: column;
                align-items: center;
            }

            .recipe-tab {
                width: 100%;
                justify-content: center;
            }

            .dish-card,
            .restaurant-card {
                max-width: 350px;
                margin: 0 auto;
            }
        }
    </style>
</head>
<body>
    <!-- Header - ORIGINAL -->
    <header>
        <div class="container header-content">
            <div class="logo">
                <h1>Sabores de <span>Salitre</span></h1>
            </div>
            <nav>
                <ul>
                    <li><a href="#inicio">Inicio</a></li>
                    <li><a href="#platillos">Platillos</a></li>
                    <li><a href="#ingredientes">Ingredientes</a></li>
                    <li><a href="#restaurantes">Restaurantes</a></li>
                    <li><a href="#recetas">Recetas</a></li>
                    <li><a href="#cultura">Cultura</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section - EXACTAMENTE IGUAL -->
    <section id="inicio" class="hero">
        <div class="hero-content">
            <h2>Descubre la Auténtica Gastronomía de Salitre</h2>
            <p>Sumérgete en los sabores tradicionales y la rica herencia culinaria de nuestro cantón, donde cada plato cuenta una historia de tradición y sabor.</p>
            <a href="#platillos" class="btn">Explorar Sabores</a>
        </div>
    </section>

    <!-- Platillos Section - COMPLETADA -->
    <section id="platillos" class="dishes">
        <div class="container">
            <div class="section-title">
                <h2>Platillos Típicos</h2>
            </div>
            
            <div class="dishes-grid">
                <!-- Cazuela de Camarón - COMPLETO -->
                <div class="dish-card" onclick="openModal('cazuela')">
                    <div class="dish-img">
                        <img src="https://images.unsplash.com/photo-1563379926898-05f4575a45d8?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Cazuela de Camarón">
                        <div class="dish-overlay">
                            <h4>Cazuela de Camarón</h4>
                            <p>Platillo insignia de Salitre con camarones del río Daule</p>
                            <button class="view-details">
                                <i class="fas fa-search-plus"></i> Ver Detalles
                            </button>
                        </div>
                    </div>
                    <div class="dish-info">
                        <h3>Cazuela de Camarón</h3>
                        <p>Preparada con plátano verde majado, refrito, maní y camarón de agua dulce, cocida en pailas de barro para realzar su sabor tradicional.</p>
                        <div class="dish-meta">
                            <div class="dish-origin">
                                <i class="fas fa-map-marker-alt"></i> Especialidad Salitreña
                            </div>
                            <a href="#cazuela-info" class="dish-link" onclick="openModal('cazuela'); return false;">
                                Ver más <i class="fas fa-arrow-right"></i>
                            </a>
                        </div>
                    </div>
                </div>

                <!-- Bollo de Pescado - COMPLETADO -->
                <div class="dish-card" onclick="openModal('bollo')">
                    <div class="dish-img">
                        <img src="https://images.unsplash.com/photo-1546069901-ba9599a7e63c?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Bollo de Pescado">
                        <div class="dish-overlay">
                            <h4>Bollo de Pescado</h4>
                            <p>Masa de plátano rellena de pescado fresco del río Daule</p>
                            <button class="view-details">
                                <i class="fas fa-search-plus"></i> Ver Detalles
                            </button>
                        </div>
                    </div>
                    <div class="dish-info">
                        <h3>Bollo de Pescado</h3>
                        <p>Masa de verde rellena de pescado y envuelta en hojas de plátano, cocida al vapor para conservar todos los sabores naturales.</p>
                        <div class="dish-meta">
                            <div class="dish-origin">
                                <i class="fas fa-fish"></i> Pescado Fresco
                            </div>
                            <a href="#bollo-info" class="dish-link" onclick="openModal('bollo'); return false;">
                                Ver más <i class="fas fa-arrow-right"></i>
                            </a>
                        </div>
                    </div>
                </div>

                <!-- Seco de Pato - COMPLETADO -->
                <div class="dish-card" onclick="openModal('seco')">
                    <div class="dish-img">
                        <img src="https://images.unsplash.com/photo-1476224203421-9ac39bcb3327?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Seco de Pato">
                        <div class="dish-overlay">
                            <h4>Seco de Pato</h4>
                            <p>Guiso tradicional cocinado con chicha de jora</p>
                            <button class="view-details">
                                <i class="fas fa-search-plus"></i> Ver Detalles
                            </button>
                        </div>
                    </div>
                    <div class="dish-info">
                        <h3>Seco de Gallina/Pato</h3>
                        <p>Cocido lentamente con chicha de jora (o cerveza), acompañado de arroz y maduros fritos glaseados con panela.</p>
                        <div class="dish-meta">
                            <div class="dish-origin">
                                <i class="fas fa-calendar-alt"></i> Fiestas Patronales
                            </div>
                            <a href="#seco-info" class="dish-link" onclick="openModal('seco'); return false;">
                                Ver más <i class="fas fa-arrow-right"></i>
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- MODALES PARA PLATILLOS -->
    <!-- Modal Cazuela de Camarón -->
    <div class="modal" id="modal-cazuela">
        <div class="modal-content">
            <div class="modal-header">
                <button class="modal-close" onclick="closeModal('cazuela')">
                    <i class="fas fa-times"></i>
                </button>
                <h3>Cazuela de Camarón Salitreña</h3>
                <div class="modal-subtitle">Patrimonio Gastronómico del Cantón Salitre</div>
            </div>
            <div class="modal-body">
                <div class="modal-image">
                    <img src="https://images.unsplash.com/photo-1563379926898-05f4575a45d8?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Cazuela de Camarón">
                </div>
                
                <div class="modal-grid">
                    <div class="modal-info">
                        <h4><i class="fas fa-history"></i> Historia</h4>
                        <p>La cazuela de camarón es un legado de las culturas ancestrales de la costa ecuatoriana. En Salitre, se prepara con camarones del río Daule, utilizando técnicas que datan de más de 200 años.</p>
                    </div>
                    
                    <div class="modal-info">
                        <h4><i class="fas fa-award"></i> Reconocimientos</h4>
                        <p>🏆 Patrimonio Cultural Inmaterial<br>
                        🥇 Tradición Centenaria<br>
                        🌟 Sello de Calidad Salitreña</p>
                    </div>
                </div>
                
                <div class="modal-info">
                    <h4><i class="fas fa-seedling"></i> Ingredientes</h4>
                    <ul class="ingredients-list">
                        <li>
                            <span class="ingredient-name">Camarones del río Daule</span>
                            <span class="ingredient-origin">Pesca artesanal</span>
                        </li>
                        <li>
                            <span class="ingredient-name">Plátano verde orgánico</span>
                            <span class="ingredient-origin">Plantaciones locales</span>
                        </li>
                        <li>
                            <span class="ingredient-name">Maní tostado salitreño</span>
                            <span class="ingredient-origin">Variedad exclusiva</span>
                        </li>
                        <li>
                            <span class="ingredient-name">Achiote natural</span>
                            <span class="ingredient-origin">Colorante ancestral</span>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="modal-footer">
                <p><strong>💡 Dato:</strong> Se cocina en paila de barro por 3-4 horas para lograr la textura perfecta.</p>
            </div>
        </div>
    </div>

    <!-- Modal Bollo de Pescado - NUEVO -->
    <div class="modal" id="modal-bollo">
        <div class="modal-content">
            <div class="modal-header">
                <button class="modal-close" onclick="closeModal('bollo')">
                    <i class="fas fa-times"></i>
                </button>
                <h3>Bollo de Pescado Salitreño</h3>
                <div class="modal-subtitle">Tradición Envuelta en Hoja de Plátano</div>
            </div>
            <div class="modal-body">
                <div class="modal-image">
                  <img src="https://images.unsplash.com/photo-1546069901-ba9599a7e63c?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Bollo de Pescado">
                </div>
                
                <div class="modal-grid">
                    <div class="modal-info">
                        <h4><i class="fas fa-history"></i> Historia</h4>
                        <p>El bollo de pescado es una técnica ancestral de cocción al vapor que las culturas costeñas han perfeccionado. En Salitre, se prepara con pescado bocachico del río Daule, envuelto en masa de plátano verde.</p>
                    </div>
                    
                    <div class="modal-info">
                        <h4><i class="fas fa-award"></i> Reconocimientos</h4>
                        <p>🏆 Tradición Familiar Centenaria<br>
                        🥇 Sello de Autenticidad<br>
                        🌟 Técnica Patrimonial</p>
                    </div>
                </div>
                
                <div class="modal-info">
                    <h4><i class="fas fa-seedling"></i> Ingredientes</h4>
                    <ul class="ingredients-list">
                        <li>
                            <span class="ingredient-name">Pescado fresco</span>
                            <span class="ingredient-origin">Río Daule</span>
                        </li>
                        <li>
                            <span class="ingredient-name">Plátano</span>
                            <span class="ingredient-origin">Cultivos locales</span>
                        </li>
                        <li>
                            <span class="ingredient-name">Hojas de plátano</span>
                            <span class="ingredient-origin">Huertas familiares</span>
                        </li>
                        <li>
                            <span class="ingredient-name">Especias secretas</span>
                            <span class="ingredient-origin">Receta familiar</span>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="modal-footer">
                <p><strong>💡 Dato:</strong> Se cuece al vapor por 1 hora, lo que permite que los sabores se concentren y la masa quede suave y húmeda.</p>
            </div>
        </div>
    </div>

    <!-- Modal Seco de Pato - NUEVO -->
    <div class="modal" id="modal-seco">
        <div class="modal-content">
            <div class="modal-header">
                <button class="modal-close" onclick="closeModal('seco')">
                    <i class="fas fa-times"></i>
                </button>
                <h3>Seco de Pato Salitreño</h3>
                <div class="modal-subtitle">Guiso Festivo de Herencia Campesina</div>
            </div>
            <div class="modal-body">
                <div class="modal-image">
                    <img src="https://images.unsplash.com/photo-1476224203421-9ac39bcb3327?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Seco de Pato">
                </div>
                
                <div class="modal-grid">
                    <div class="modal-info">
                        <h4><i class="fas fa-history"></i> Historia</h4>
                        <p>El seco de pato es un plato festivo que se prepara en las celebraciones importantes del cantón Salitre. La receta original incluye chicha de jora, una bebida fermentada de maíz que le da un sabor único.</p>
                    </div>
                    
                    <div class="modal-info">
                        <h4><i class="fas fa-award"></i> Reconocimientos</h4>
                        <p>🏆 Plato Festivo Tradicional<br>
                        🥇 Mejor Sabor 2026<br>
                        🌟 Patrimonio Cultural Inmaterial</p>
                    </div>
                </div>
                
                <div class="modal-info">
                    <h4><i class="fas fa-seedling"></i> Ingredientes</h4>
                    <ul class="ingredients-list">
                        <li>
                            <span class="ingredient-name">Pato criollo</span>
                            <span class="ingredient-origin">Granjas locales</span>
                        </li>
                        <li>
                            <span class="ingredient-name">Chicha de jora</span>
                            <span class="ingredient-origin">Elaboración artesanal</span>
                        </li>
                        <li>
                            <span class="ingredient-name">Cerveza (alternativa)</span>
                            <span class="ingredient-origin">Para quienes no usan chicha</span>
                        </li>
                        <li>
                            <span class="ingredient-name">Cebolla, ajo, pimiento</span>
                            <span class="ingredient-origin">Huertos familiares</span>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="modal-footer">
                <p><strong>💡 Dato:</strong> Se cocina a fuego lento por 2-3 horas hasta que el pato esté tan suave que se desprende del hueso.</p>
            </div>
        </div>
    </div>

    <!-- Ingredientes Section - MEJORADA -->
    <section id="ingredientes" class="ingredients">
        <div class="container">
            <div class="section-title">
                <h2>Ingredientes Autóctonos</h2>
            </div>
            <div class="ingredients-grid">
                <div class="ingredient-card">
                    <div class="ingredient-icon">
                        <i class="fas fa-shrimp"></i>
                    </div>
                    <h3>Camarón de Río</h3>
                    <p>Extraído del río Daule, de sabor dulce y textura firme. Fundamental para la cazuela salitreña.</p>
                </div>
                <div class="ingredient-card">
                    <div class="ingredient-icon">
                        <i class="fas fa-fish"></i>
                    </div>
                    <h3>Pescado</h3>
                    <p>Especie endémica del río Daule, de carne blanca y escasas espinas. Ideal para bollos tradicionales.</p>
                </div>
                <div class="ingredient-card">
                    <div class="ingredient-icon">
                        <i class="fas fa-leaf"></i>
                    </div>
                    <h3>Plátano Verde</h3>
                    <p>Cultivado en las riberas del Daule, se utiliza majado para masas y hervido como acompañante.</p>
                </div>
                <div class="ingredient-card">
                    <div class="ingredient-icon">
                        <i class="fas fa-seedling"></i>
                    </div>
                    <h3>Maní Salitreño</h3>
                    <p>Variedad especial tostada y molida que da espesor y sabor único a guisos y refritos tradicionales.</p>
                </div>


<div class="ingredient-card">
                    <div class="ingredient-icon">
                        <i class="fas fa-seedling"></i>
                    </div>
                    <h3>Choclo Tierno</h3>
                    <p>Mazorca con granos más dulces y blandos, ideal para humitas, tamales y sopas como el caldo de manguera..</p>
                </div>

<div class="ingredient-card">
                    <div class="ingredient-icon">
                        <i class="fas fa-seedling"></i>
                    </div>
                    <h3>Leche Recién Ordeñada (de Ganado Criollo)</h3>
                    <p>Base para preparar el queso fresco, natilla, y bebidas como el vino de leche (bebida caliente con especias </p>
                </div>






            </div>
        </div>
    </section>
                        
    <!-- Restaurantes Section - MEJORADA -->
    <section id="restaurantes" class="restaurants">
        <div class="container">
            <div class="section-title">
                <h2>Restaurantes Destacados</h2>
            </div>
            <div class="restaurants-grid">
                <div class="restaurant-card">
                    <div class="restaurant-img">
                        <img src="https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="El Sabor Costeño">
                        <div class="restaurant-badge">⭐ 4.7</div>
                    </div>
                    <div class="restaurant-info">
                        <h3>EL BUEN SABOR </h3>
                        <div class="restaurant-rating">
                            <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star-half-alt"></i>
                            4.7 (342 reseñas)
                        </div>
                        <p>Especializado en platos tradicionales con más de 20 años de experiencia familiar.</p>
                        <div class="restaurant-features">
                            <div class="feature">
                                <i class="fas fa-clock"></i> 6:00 AM - 5:30 PM
                            </div>
                            <div class="feature">
                                <i class="fas fa-dollar-sign"></i> $ - $$
                            </div>
                            <div class="feature">
                                <i class="fas fa-utensils"></i> Tradicional
                            </div>
                        </div>
                        <a href="#" class="restaurant-link" onclick="alert('📞 Contacto: 04-2789-123\n📍 Dirección: Av. Principal #123, Salitre Centro\n\n¡Gracias por su interés!'); return false;">
                            <i class="fas fa-phone-alt"></i> Reservar Mesa
                        </a>
                    </div>
                </div>
                
                <div class="restaurant-card">
                    <div class="restaurant-img">
                        <img src="https://images.unsplash.com/photo-1555396273-367ea4eb4db5?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="La Casa del Pescador">
                        <div class="restaurant-badge">⭐ 4.5</div>
                    </div>
                    <div class="restaurant-info">
                        <h3>LA CABAÑA DE MERCEDES</h3>
                        <div class="restaurant-rating">
                            <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="far fa-star"></i>
                            4.5 (287 reseñas)
                        </div>
                        <p>Secos de pollo y bollos de pescado que atraen a turistas de toda la región.</p>
                        <div class="restaurant-features">
                            <div class="feature">
                                <i class="fas fa-clock"></i> 7:00 AM - 5:00 PM
                            </div>
                            <div class="feature">
                                <i class="fas fa-dollar-sign"></i> $$
                            </div>
                            <div class="feature">
                                <i class="fas fa-water"></i> Vista al río
                            </div>
                        </div>
                        <a href="#" class="restaurant-link" onclick="alert('📞 Contacto: 04-2789-456\n📍 Dirección: Calle de los Mariscos #456, Salitre\n\n¡Esperamos su visita!'); return false;">
                            <i class="fas fa-phone-alt"></i> Reservar Mesa
                        </a>
                    </div>
                </div>
                
                <div class="restaurant-card">
                    <div class="restaurant-img">
                        <img src="https://images.unsplash.com/photo-1590846406792-0adc7f938f1d?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Sabores de la Abuela">
                        <div class="restaurant-badge">⭐ 4.8</div>
                    </div>
                    <div class="restaurant-info">
                        <h3>SABORES DE LA ABUELA</h3>
                        <div class="restaurant-rating">
                            <i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i>
                            4.8 (412 reseñas)
                        </div>
                        <p>Recetas tradicionales transmitidas por 3 generaciones en ambiente familiar acogedor.</p>
                        <div class="restaurant-features">
                            <div class="feature">
                                <i class="fas fa-clock"></i> 7:00 AM - 6:00 PM
                            </div>
                            <div class="feature">
                                <i class="fas fa-dollar-sign"></i> $
                            </div>
                            <div class="feature">
                                <i class="fas fa-home"></i> Familiar
                            </div>
                        </div>
                        <a href="#" class="restaurant-link" onclick="alert('📞 Contacto: 04-2789-789\n📍 Dirección: Barrio Central #789, Salitre\n\n¡Hogar de los sabores tradicionales!'); return false;">
                            <i class="fas fa-phone-alt"></i> Reservar Mesa
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Recetas Section - MEJORADA -->
    <section id="recetas" class="recipes">
        <div class="container">
            <div class="section-title">
                <h2>Recetas Tradicionales</h2>
            </div>
            <div class="recipe-tabs">
                <button class="recipe-tab active" data-target="encebollado">
                    <i class="fas fa-shrimp"></i> Cazuela de camaron
                </button>
                <button class="recipe-tab" data-target="ceviche">
                    <i class="fas fa-lemon"></i> Bollo de pescado
                </button>
                <button class="recipe-tab" data-target="arroz">
                    <i class="fas fa-utensils"></i> Seco de pato
                </button>
            </div>

            <div class="recipe-content active" id="encebollado">
                <div class="recipe-details">
                    <div class="recipe-ingredients">
                        <h4><i class="fas fa-shopping-basket"></i> Ingredientes</h4>
                        <ul>
                            <li><i class="fas fa-check"></i> ✅ 2 lbs camarones de río</li>
                            <li><i class="fas fa-check"></i> ✅ 6 plátanos verdes </li>
                            <li><i class="fas fa-check"></i> ✅ 1 taza maní tostado </li>
                            <li><i class="fas fa-check"></i> ✅ 2 cebollas coloradas </li>
                            <li><i class="fas fa-check"></i> ✅ 4 dientes de ajo </li>
                            <li><i class="fas fa-check"></i> ✅ 1 cda achiote </li>
                            <li><i class="fas fa-check"></i> ✅ Rama de cilantro</li>
                        </ul>
                    </div>
                    <div class="recipe-steps">
                        <h4><i class="fas fa-list-ol"></i> Preparación</h4>
                        <div class="recipe-step">
                            Paso 1: Limpiar los camarones, reservando las cabezas para el caldo.
                        </div>
                        <div class="recipe-step">
                            Paso 2: Pelar y rallar los plátanos verdes. Amasar con sal hasta obtener consistencia homogénea.
                        </div>
                        <div class="recipe-step">
                           Paso 3: Tostar y moler el maní. Preparar refrito con cebolla, ajo, achiote y especias.
                        </div>
                        <div class="recipe-step">
                            Paso 4: Cocinar todo en paila de barro a fuego lento por 2 horas, removiendo cada 20 minutos.
                        </div>
                        <div class="recipe-step">
                           Paso 5: Rectificar sal y servir caliente con los acompañamientos.
                        </div>
                    </div>
                </div>
            </div>

            <div class="recipe-content" id="ceviche">
                <div class="recipe-details">
                    <div class="recipe-ingredients">
                        <h4><i class="fas fa-shopping-basket"></i> Ingredientes</h4>
                        <ul>
                            <li><i class="fas fa-check"></i> ✅ 2 libras de pescado bocachico</li>
                            <li><i class="fas fa-check"></i> ✅ 8 plátanos verdes</li>
                            <li><i class="fas fa-check"></i> ✅ Hojas de plátano</li>
                            <li><i class="fas fa-check"></i> ✅ 1 cebolla blanca picada</li>
                            <li><i class="fas fa-check"></i> ✅ 2 tomates maduros</li>
                            <li><i class="fas fa-check"></i> ✅ Cilantro picado</li>
                            <li><i class="fas fa-check"></i> ✅ Sal, pimienta y comino</li>
                        </ul>
                    </div>
                    <div class="recipe-steps">
                        <h4><i class="fas fa-list-ol"></i> Preparación</h4>
                        <div class="recipe-step">
                          Paso 1: Limpiar y filetear el pescado, cortarlo en trozos medianos.
                        </div>
                        <div class="recipe-step">
                          Paso 2: Pelar y rallar los plátanos verdes. Amasar hasta formar una masa homogénea.
                        </div>
                        <div class="recipe-step">
                          Paso 3: Mezclar el pescado con cebolla, tomate, cilantro y especias.
                        </div>
                        <div class="recipe-step">
                          Paso 4: Formar bollos con la masa, rellenar con la mezcla de pescado y envolver en hojas de plátano.
                        </div>
                        <div class="recipe-step">
                          Paso 5: Cocinar al vapor por 45-60 minutos hasta que la masa esté cocida.
                        </div>
                    </div>
                </div>
            </div>

            <div class="recipe-content" id="arroz">
                <div class="recipe-details">
                    <div class="recipe-ingredients">
                        <h4><i class="fas fa-shopping-basket"></i> Ingredientes</h4>
                        <ul>
                            <li><i class="fas fa-check"></i> ✅ 1 pato entero troceado</li>
                            <li><i class="fas fa-check"></i> ✅ 2 tazas de chicha de jora</li>
                            <li><i class="fas fa-check"></i> ✅ 3 cebollas coloradas</li>
                            <li><i class="fas fa-check"></i> ✅ 4 dientes de ajo</li>
                            <li><i class="fas fa-check"></i> ✅ Pimiento, cilantro, culantro</li>
                            <li><i class="fas fa-check"></i> ✅ Sal, pimienta y comino</li>
                            <li><i class="fas fa-check"></i> ✅ Arroz y maduros para acompañar</li>
                        </ul>
                    </div>
                    <div class="recipe-steps">
                        <h4><i class="fas fa-list-ol"></i> Preparación</h4>
                        <div class="recipe-step">
                          Paso 1: Dorar los trozos de pato en aceite caliente hasta que queden dorados.
                        </div>
                        <div class="recipe-step">
                          Paso 2: Preparar un refrito con cebolla, ajo, pimiento y especias.
                        </div>
                        <div class="recipe-step">
                          Paso 3: Añadir el pato dorado al refrito y cubrir con la chicha de jora.
                        </div>
                        <div class="recipe-step">
                          Paso 4: Cocinar a fuego lento por 2-3 horas hasta que el pato esté tierno.
                        </div>
                        <div class="recipe-step">
                          Paso 5: Servir con arroz blanco y maduros fritos.
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Cultura Section - MEJORADA -->
    <section id="cultura" class="culture">
        <div class="container">
            <div class="section-title">
                <h2>Cultura Gastronómica</h2>
            </div>
            <div class="culture-content">
                <div class="culture-text">
                   
                    <p>La gastronomía de Salitre es el resultado de una rica herencia cultural que combina técnicas ancestrales con ingredientes locales de la más alta calidad. Nuestros platos representan la identidad costeña y la conexión con el mar y la tierra.</p>
                    <p>Las recetas han sido transmitidas de generación en generación, preservando los sabores auténticos que hacen única a nuestra cocina. Cada platillo cuenta una historia de pescadores, agricultores y familias que han hecho de la comida un arte.</p>
                    <p>En Salitre, la comida es más que nutrición; es un acto de comunión, celebración y preservación de nuestras tradiciones. Te invitamos a vivir esta experiencia gastronómica que despierta todos los sentidos.</p>
                    <a href="#restaurantes" class="btn" style="margin-top: 1.5rem;">
                        <i class="fas fa-utensils"></i> Descubrir Restaurantes
                    </a>
                </div>
               
                    <div class="culture-img">
                        <img src="https://images.unsplash.com/photo-1563379926898-05f4575a45d8?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Cazuela de Camarón">
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer - MEJORADO -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>Sabores de Salitre</h3>
                    <p>Promoviendo la riqueza gastronómica del Cantón Salitre, Ecuador. Descubre, saborea y comparte nuestra tradición culinaria centenaria.</p>
                    <p>Proyecto dedicado a la preservación del patrimonio gastronómico local.</p>
                </div>
                
                <div class="footer-section">
                    <h3>Contacto</h3>
                    <div class="contact-info">
                        <i class="fas fa-map-marker-alt"></i>
                        <span>Cantón Salitre, Guayas, Ecuador</span>
                    </div>
                    <div class="contact-info">
                        <i class="fas fa-phone"></i>
                        <span>+593 986 437 868</span>
                    </div>
                    <div class="contact-info">
                        <i class="fas fa-envelope"></i>
                        <span>maximo.joel0101@gmail.com</span>
                    </div>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-youtube"></i></a>
                    </div>
                </div>
                
                <div class="footer-section quick-links">
                    <h3>Enlaces Rápidos</h3>
                    <ul>
                        <li><a href="#inicio"><i class="fas fa-chevron-right"></i> Inicio</a></li>
                        <li><a href="#platillos"><i class="fas fa-chevron-right"></i> Platillos</a></li>
                        <li><a href="#ingredientes"><i class="fas fa-chevron-right"></i> Ingredientes</a></li>
                        <li><a href="#restaurantes"><i class="fas fa-chevron-right"></i> Restaurantes</a></li>
                        <li><a href="#recetas"><i class="fas fa-chevron-right"></i> Recetas</a></li>
                        <li><a href="#cultura"><i class="fas fa-chevron-right"></i> Cultura</a></li>
                    </ul>
                </div>
            </div>
            
            <div class="footer-bottom">
                <p>&copy; 2026 Sabores de Salitre. Todos los derechos reservados. | Proyecto de Desarrollo Web</p>
            </div>
        </div>
    </footer>

  
     
      
    <script>
        // Sistema de modales
        function openModal(dishId) {
            const modal = document.getElementById(`modal-${dishId}`);
            if(modal) {
                modal.classList.add('active');
                document.body.style.overflow = 'hidden';
            }
        }

        function closeModal(dishId) {
            const modal = document.getElementById(`modal-${dishId}`);
            if(modal) {
                modal.classList.remove('active');
                document.body.style.overflow = 'auto';
            }
        }

        // Navegación suave
        document.querySelectorAll('nav a, .dish-link, .restaurant-link, .btn, .quick-links a').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                if(this.getAttribute('href').startsWith('#')) {
                    e.preventDefault();
                    const targetId = this.getAttribute('href');
                    if(targetId !== '#') {
                        const targetElement = document.querySelector(targetId);
                        window.scrollTo({
                            top: targetElement.offsetTop - 80,
                            behavior: 'smooth'
                        });
                    }
                }
            });
        });

        // Tabs de recetas
        const recipeTabs = document.querySelectorAll('.recipe-tab');
        recipeTabs.forEach(tab => {
            tab.addEventListener('click', () => {
                // Remover clase active de todos
                document.querySelectorAll('.recipe-tab').forEach(t => t.classList.remove('active'));
                document.querySelectorAll('.recipe-content').forEach(c => c.classList.remove('active'));
                
                // Agregar clase active al tab clickeado
                tab.classList.add('active');
                
                // Mostrar contenido correspondiente
                const targetId = tab.getAttribute('data-target');
                document.getElementById(targetId).classList.add('active');
            });
        });

        // Cerrar modal al hacer clic fuera
        document.querySelectorAll('.modal').forEach(modal => {
            modal.addEventListener('click', function(e) {
                if(e.target === this) {
                    this.classList.remove('active');
                    document.body.style.overflow = 'auto';
                }
            });
        });

        // Cerrar modal con ESC
        document.addEventListener('keydown', (e) => {
            if(e.key === 'Escape') {
                document.querySelectorAll('.modal').forEach(modal => {
                    if(modal.classList.contains('active')) {
                        closeModal(modal.id.replace('modal-', ''));
                    }
                });
            }
        });

        // Animaciones al hacer scroll
        const observerOptions = {
            root: null,
            rootMargin: '0px',
            threshold: 0.1
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                    observer.unobserve(entry.target);
                }
            });
        }, observerOptions);

        // Observar elementos para animación
        document.querySelectorAll('.dish-card, .ingredient-card, .restaurant-card, .culture-img').forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(30px)';
            card.style.transition = 'opacity 0.8s ease, transform 0.8s ease';
            observer.observe(card);
        });

        // Header scroll effect
        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            if(window.scrollY > 100) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });

        // Contador de visitas
        if(!localStorage.getItem('visitasSalitre')) {
            localStorage.setItem('visitasSalitre', '1');
        } else {
            let visitas = parseInt(localStorage.getItem('visitasSalitre'));
            visitas++;
            localStorage.setItem('visitasSalitre', visitas.toString());
        }

        // Inicialización
        window.addEventListener('load', () => {
            console.log(`🌮 Sabores de Salitre | Visitas: ${localStorage.getItem('visitasSalitre')}`);
            
            // Efecto de carga
            document.body.style.opacity = '0';
            document.body.style.transition = 'opacity 0.6s ease';
            
            setTimeout(() => {
                document.body.style.opacity = '1';
            }, 100);
        });

        // Efecto hover en tarjetas de restaurantes
        document.querySelectorAll('.restaurant-card').forEach(card => {
            card.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-15px) scale(1.02)';
            });
            
            card.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0) scale(1)';
            });
        });
    </script>
</body>
</html>
