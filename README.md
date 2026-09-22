<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portal Oficial | Conselho Tutelar de Breves e Marajó-PA</title>
    
    <!-- Fontes Oficiais e Ícones -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Montserrat:wght@700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root {
            --primary: #0f172a;    
            --secondary: #3b82f6;  
            --secondary-dark: #2563eb;
            --accent: #ef4444;     
            --success: #10b981;    
            --bg: #f8fafc;         
            --card-bg: #ffffff;
            --text-main: #334155;
            --text-muted: #64748b;
            --border-light: #e2e8f0;
            --glass-bg: rgba(255, 255, 255, 0.88);
            --focus-ring: 0 0 0 3px rgba(59, 130, 246, 0.4);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }
        
        body { 
            font-family: 'Inter', sans-serif; 
            background: linear-gradient(135deg, #f8fafc 0%, #f1f5f9 100%);
            color: var(--text-main); 
            line-height: 1.6; 
            overflow-x: hidden;
        }

        /* Foco e Acessibilidade */
        :focus-visible {
            outline: none;
            box-shadow: var(--focus-ring);
        }

        .sr-only {
            position: absolute;
            width: 1px;
            height: 1px;
            padding: 0;
            margin: -1px;
            overflow: hidden;
            clip: rect(0, 0, 0, 0);
            border: 0;
        }

        .gov-bar { 
            background: linear-gradient(90deg, #020617, #0f172a); 
            color: #fff; 
            padding: 8px 5%; 
            font-size: 11px; 
            display: flex; 
            justify-content: space-between; 
            text-transform: uppercase; 
            letter-spacing: 1.5px; 
            font-weight: 600; 
        }

        header { 
            background: var(--glass-bg); 
            backdrop-filter: blur(12px); 
            padding: 20px 5%; 
            border-bottom: 1px solid rgba(255,255,255,0.3); 
            box-shadow: 0 4px 30px rgba(0, 0, 0, 0.05); 
            position: sticky; 
            top: 0; 
            z-index: 1000; 
        }

        .header-container { 
            max-width: 1200px; 
            margin: 0 auto; 
            display: flex; 
            align-items: center; 
            gap: 20px; 
        }

        .logo-box { 
            background: linear-gradient(135deg, var(--secondary), var(--secondary-dark)); 
            color: white; 
            width: 60px; 
            height: 60px; 
            border-radius: 14px; 
            display: flex; 
            align-items: center; 
            justify-content: center; 
            font-size: 26px; 
            box-shadow: 0 10px 15px -3px rgba(59, 130, 246, 0.4); 
            transform: rotate(-3deg); 
            flex-shrink: 0;
        }

        .header-titles h1 { 
            color: var(--primary); 
            font-family: 'Montserrat', sans-serif; 
            font-size: 22px; 
            font-weight: 800; 
            line-height: 1.1;
        }

        .header-titles p { 
            color: var(--secondary); 
            font-size: 12px; 
            font-weight: 700; 
            letter-spacing: 1px; 
            margin-top: 4px;
        }

        nav { padding: 20px 5% 0; }
        .nav-container { 
            max-width: 1200px; 
            margin: 0 auto; 
            display: flex; 
            background: var(--card-bg); 
            padding: 6px; 
            border-radius: 100px; 
            box-shadow: 0 4px 20px rgba(0,0,0,0.03); 
            border: 1px solid var(--border-light); 
            overflow-x: auto; 
            scrollbar-width: thin;
            position: relative;
        }

        .nav-link { 
            background: transparent; 
            color: var(--text-muted); 
            border: none; 
            font-family: 'Inter', sans-serif; 
            padding: 12px 20px; 
            font-size: 13px; 
            font-weight: 600; 
            border-radius: 100px; 
            cursor: pointer; 
            transition: all 0.3s ease; 
            white-space: nowrap; 
            display: flex; 
            align-items: center; 
            gap: 8px;
        }
        .nav-link:hover { color: var(--primary); background: #f1f5f9; }
        .nav-link.active { background: var(--primary); color: white; box-shadow: 0 4px 10px rgba(15, 23, 42, 0.2); }

        .container { 
            max-width: 1200px; 
            margin: 30px auto 60px; 
            padding: 0 5%; 
            display: grid; 
            grid-template-columns: 1fr 350px; 
            gap: 30px; 
            min-height: 600px; 
        }

        .content-section { display: none; animation: slideUp 0.4s cubic-bezier(0.16, 1, 0.3, 1); }
        .content-section.active { display: block; }

        @keyframes slideUp { from { opacity: 0; transform: translateY(15px); } to { opacity: 1; transform: translateY(0); } }

        .main-card { 
            background: var(--card-bg); 
            padding: 40px; 
            border-radius: 20px; 
            box-shadow: 0 10px 30px -10px rgba(0, 0, 0, 0.05); 
            border: 1px solid var(--border-light); 
        }
        
        .city-hero-img { 
            width: 100%; 
            height: 350px; 
            object-fit: cover; 
            border-radius: 16px; 
            margin-bottom: 30px; 
            box-shadow: 0 10px 25px rgba(0,0,0,0.05); 
            transition: opacity 0.3s ease;
        }

        .badge { 
            display: inline-flex; 
            align-items: center; 
            gap: 6px; 
            padding: 6px 14px; 
            background: #eff6ff; 
            border-radius: 20px; 
            font-size: 11px; 
            font-weight: 700; 
            color: var(--secondary); 
            margin-bottom: 15px; 
            text-transform: uppercase; 
            border: 1px solid #dbeafe;
        }

        .title-highlight { 
            font-family: 'Montserrat', sans-serif; 
            font-size: 28px; 
            color: var(--primary); 
            line-height: 1.2; 
            letter-spacing: -0.5px; 
            margin-bottom: 15px;
        }

        .text-spacing { font-size: 16px; color: var(--text-main); margin-bottom: 25px; line-height: 1.7;}
        
        .services-list { list-style: none; margin-top: 20px; display: flex; flex-direction: column; gap: 15px; }
        .services-list li { 
            display: flex; 
            align-items: flex-start; 
            gap: 12px; 
            font-size: 15px; 
            color: var(--text-main); 
            line-height: 1.5; 
            background: #f8fafc; 
            padding: 15px 20px; 
            border-radius: 12px; 
            border: 1px solid var(--border-light); 
            transition: transform 0.2s, border-color 0.2s; 
        }
        .services-list li:hover { transform: translateX(5px); border-color: var(--secondary); }
        .services-list i { color: var(--secondary); font-size: 18px; margin-top: 2px; flex-shrink: 0; }

        .law-box { 
            background: linear-gradient(to right, #f8fafc, #ffffff); 
            padding: 25px; 
            border-radius: 12px; 
            border-left: 5px solid var(--secondary); 
            border-top: 1px solid var(--border-light);
            border-right: 1px solid var(--border-light);
            border-bottom: 1px solid var(--border-light);
            margin-bottom: 20px;
            position: relative;
        }

        #law-title { color: var(--primary); font-family: 'Montserrat', sans-serif; font-size: 17px; margin-bottom: 8px;}
        .law-text { font-style: italic; color: var(--text-muted); font-size: 15px; transition: opacity 0.3s ease; }
        
        .law-controls { display: flex; gap: 10px; margin-top: 15px; justify-content: flex-end; }
        .law-btn { background: var(--bg); border: 1px solid var(--border-light); padding: 6px 12px; border-radius: 6px; font-size: 12px; cursor: pointer; color: var(--text-muted); transition: 0.2s; }
        .law-btn:hover { background: var(--secondary); color: white; border-color: var(--secondary); }

        .news-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 20px; }
        .news-item { 
            background: var(--card-bg); 
            border: 1px solid var(--border-light); 
            border-radius: 12px; 
            overflow: hidden; 
            transition: transform 0.3s ease, box-shadow 0.3s ease; 
            display: flex;
            flex-direction: column;
            position: relative;
        }
        .news-item:hover { transform: translateY(-5px); box-shadow: 0 15px 25px -5px rgba(0,0,0,0.1); border-color: var(--secondary); }
        .news-img { width: 100%; height: 160px; background: #f1f5f9; display: flex; align-items: center; justify-content: center; color: var(--text-muted); overflow: hidden;}
        .news-img img { width: 100%; height: 100%; object-fit: cover; }
        .news-body { padding: 20px; flex-grow: 1; }
        .news-body h4 { font-size: 16px; color: var(--primary); margin-bottom: 8px; font-family: 'Montserrat', sans-serif; line-height: 1.3;}
        .news-body p { font-size: 13px; color: var(--text-muted); line-height: 1.5; }
        .delete-news-btn { 
            position: absolute; 
            top: 10px; 
            right: 10px; 
            background: rgba(239, 68, 68, 0.95); 
            color: white; 
            border: none; 
            padding: 6px 12px; 
            border-radius: 6px; 
            font-size: 11px; 
            font-weight: 600;
            cursor: pointer; 
            opacity: 0; 
            transition: opacity 0.2s, background 0.2s; 
            box-shadow: 0 2px 6px rgba(0,0,0,0.2);
        }
        .news-item:hover .delete-news-btn, .delete-news-btn:focus { opacity: 1; }
        .delete-news-btn:hover { background: #dc2626; }

        .duty-box { background: linear-gradient(135deg, #eff6ff 0%, #dbeafe 100%); border-radius: 16px; padding: 25px; margin-bottom: 35px; border: 1px solid #bfdbfe;}
        .duty-title { color: var(--secondary-dark); font-weight: 800; font-size: 14px; margin-bottom: 15px; display: flex; align-items: center; justify-content: space-between;}
        .duty-person { display: flex; justify-content: space-between; padding: 12px 0; border-bottom: 1px solid rgba(59, 130, 246, 0.2); font-size: 14px; align-items: center;}
        .duty-person:last-child { border-bottom: none; padding-bottom: 0; }
        
        .staff-list { display: flex; flex-direction: column; gap: 12px; }
        .staff-card { display: flex; align-items: center; gap: 15px; padding: 15px; background: var(--bg); border: 1px solid var(--border-light); border-radius: 12px; transition: background 0.2s;}
        .staff-card:hover { background: #fff; }
        .avatar { width: 45px; height: 45px; background: #e2e8f0; border-radius: 50%; display: flex; align-items: center; justify-content: center; color: var(--text-muted); font-size: 18px; }
        .staff-info strong { color: var(--primary); font-size: 14px; display: block; margin-bottom: 2px;}
        .staff-role { font-size: 12px; color: var(--text-muted); font-weight: 500; }

        .admin-card { background: #f8fafc; border: 1px solid var(--border-light); border-radius: 12px; padding: 25px; margin-bottom: 20px;}
        .admin-card h4 { color: var(--primary); margin-bottom: 18px; font-family: 'Montserrat', sans-serif; display: flex; align-items: center; gap: 8px; font-size: 16px;}
        .admin-label { display: block; font-size: 12px; font-weight: 700; color: var(--text-muted); margin-bottom: 6px; text-transform: uppercase; letter-spacing: 0.5px;}
        .admin-input { width: 100%; padding: 12px 15px; border-radius: 8px; border: 1px solid #cbd5e1; margin-bottom: 20px; font-family: 'Inter', sans-serif; font-size: 14px; background: #fff; transition: border 0.3s;}
        .admin-input:focus { outline: none; border-color: var(--secondary); box-shadow: var(--focus-ring);}
        
        input[type="file"] { padding: 8px; font-size: 13px; color: var(--text-muted); }
        input[type="file"]::file-selector-button { background: var(--bg); border: 1px solid var(--border-light); padding: 8px 12px; border-radius: 6px; color: var(--text-main); cursor: pointer; font-weight: 600; margin-right: 15px; transition: 0.2s;}
        input[type="file"]::file-selector-button:hover { background: #e2e8f0; }

        .admin-btn { 
            background: var(--primary); 
            color: white; 
            padding: 14px 20px; 
            border: none; 
            border-radius: 8px; 
            font-weight: 600; 
            cursor: pointer; 
            transition: all 0.3s; 
            width: 100%; 
            font-size: 14px; 
            display: flex; 
            justify-content: center; 
            align-items: center; 
            gap: 8px;
        }
        .admin-btn:hover { background: var(--secondary-dark); }
        .admin-btn:disabled { opacity: 0.7; cursor: not-allowed; }
        .admin-btn-success { background: var(--success); }
        .admin-btn-success:hover { background: #059669; }

        /* Spinner de Carregamento para Acessibilidade/Feedback */
        .spinner {
            display: inline-block;
            width: 16px;
            height: 16px;
            border: 2px solid rgba(255,255,255,0.3);
            border-radius: 50%;
            border-top-color: #fff;
            animation: spin 0.8s linear infinite;
        }
        @keyframes spin { to { transform: rotate(360deg); } }

        .widget { background: var(--card-bg); padding: 25px; border-radius: 20px; border: 1px solid var(--border-light); margin-bottom: 20px; box-shadow: 0 4px 15px rgba(0,0,0,0.02);}
        .widget-title { font-size: 14px; font-weight: 800; text-transform: uppercase; color: var(--primary); margin-bottom: 20px; display: flex; align-items: center; gap: 10px; }
        .widget-title::before { content: ''; display: block; width: 5px; height: 16px; background: var(--secondary); border-radius: 4px; }
        
        .select-field { 
            width: 100%; 
            padding: 14px; 
            border-radius: 10px; 
            border: 2px solid var(--border-light); 
            font-weight: 600; 
            cursor: pointer; 
            color: var(--text-main); 
            font-family: 'Inter', sans-serif; 
            background-color: var(--bg); 
            font-size: 14px; 
            appearance: none; 
            background-image: url("data:image/svg+xml;charset=UTF-8,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='none' stroke='currentColor' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'%3e%3cpolyline points='6 9 12 15 18 9'%3e%3c/polyline%3e%3c/svg%3e"); 
            background-repeat: no-repeat; 
            background-position: right 15px center; 
            background-size: 15px;
        }
        .select-field:focus { outline: none; border-color: var(--secondary); }
        
        .btn-wa { display: none; margin-top: 15px; background: linear-gradient(135deg, #10b981, #059669); color: white; text-decoration: none; padding: 14px; border-radius: 10px; text-align: center; font-weight: 700; font-size: 14px; transition: transform 0.2s;}
        .btn-wa:hover { transform: translateY(-2px); box-shadow: 0 4px 12px rgba(16, 185, 129, 0.3);}
        
        .emergency-box { background: linear-gradient(135deg, #fff1f2, #ffe4e6); border-radius: 20px; padding: 25px; border: 1px solid #fecdd3; text-align: center; margin-bottom: 20px;}
        .btn-panic { display: flex; align-items: center; justify-content: center; gap: 8px; padding: 14px; border-radius: 10px; text-decoration: none; color: white; font-weight: 800; margin-top: 10px; font-size: 13px; transition: opacity 0.2s;}
        .btn-panic:hover { opacity: 0.9; }
        .btn-primary-bg { background: var(--primary); }
        .btn-accent-bg { background: linear-gradient(135deg, #ef4444, #dc2626); box-shadow: 0 4px 12px rgba(239, 68, 68, 0.3);}
        
        .contact-info p { font-size: 13px; color: var(--text-main); margin-bottom: 15px; display: flex; align-items: flex-start; gap: 12px; line-height: 1.5;}
        .contact-info p:last-child { margin-bottom: 0;}
        .contact-info p i { color: var(--secondary); margin-top: 3px; font-size: 16px; width: 16px; text-align: center;}

        footer { background: var(--primary); color: white; padding: 40px 5%; text-align: center; border-top: 4px solid var(--secondary); font-size: 13px; color: #cbd5e1;}
        footer strong { color: white; }

        .toast-container { position: fixed; bottom: 20px; right: 20px; z-index: 9999; display: flex; flex-direction: column; gap: 10px; }
        .toast { background: white; color: var(--text-main); padding: 15px 20px; border-radius: 8px; box-shadow: 0 10px 30px rgba(0,0,0,0.1); border-left: 5px solid var(--success); font-size: 14px; font-weight: 500; display: flex; align-items: center; gap: 10px; transform: translateX(120%); transition: transform 0.3s cubic-bezier(0.68, -0.55, 0.265, 1.55); }
        .toast.show { transform: translateX(0); }
        .toast.error { border-left-color: var(--accent); }
        .toast.warning { border-left-color: #f59e0b; }

        @media (max-width: 900px) { 
            .container { grid-template-columns: 1fr; gap: 20px; padding: 0 20px;} 
            .nav-container { border-radius: 8px; } 
            .main-card { padding: 25px; }
            .city-hero-img { height: 250px; }
            .header-container { flex-direction: column; text-align: center; gap: 10px;}
        }
    </style>
</head>
<body>

<div id="toast-container" class="toast-container" aria-live="polite"></div>

<div class="gov-bar">
    <span>Portal da Transparência - Breves/PA</span>
    <span>Acesso à Informação <i class="fas fa-universal-access" aria-hidden="true"></i></span>
</div>

<header>
    <div class="header-container">
        <div class="logo-box" aria-hidden="true"><i class="fas fa-shield-halved"></i></div>
        <div class="header-titles">
            <h1>Conselho Tutelar</h1>
            <p>MUNICÍPIO DE BREVES E MARAJÓ</p>
        </div>
    </div>
</header>

<nav aria-label="Navegação Principal">
    <div class="nav-container" role="tablist">
        <button class="nav-link active" data-target="home" role="tab" aria-selected="true" aria-current="page"><i class="fas fa-home" aria-hidden="true"></i> Início</button>
        <button class="nav-link" data-target="servicos" role="tab" aria-selected="false"><i class="fas fa-concierge-bell" aria-hidden="true"></i> Serviços</button>
        <button class="nav-link" data-target="eca" role="tab" aria-selected="false"><i class="fas fa-book-open" aria-hidden="true"></i> O ECA</button>
        <button class="nav-link" data-target="noticias" role="tab" aria-selected="false"><i class="fas fa-newspaper" aria-hidden="true"></i> Notícias</button>
        <button class="nav-link" data-target="conselheiros" role="tab" aria-selected="false"><i class="fas fa-users" aria-hidden="true"></i> Equipe e Plantão</button>
        <button class="nav-link" data-target="admin" role="tab" aria-selected="false" style="color: var(--accent); font-weight: 700;"><i class="fas fa-lock" aria-hidden="true"></i> Restrito</button>
    </div>
</nav>

<div class="container">
    <main class="main-card">
        
        <!-- SEÇÃO: INÍCIO -->
        <section id="home" class="content-section active" aria-labelledby="home-title">
            <img src="https://encrypted-tbn2.gstatic.com/licensed-image?q=tbn:ANd9GcQNApHxECZLFzOATIMu9NAeQfuQKcyuo-cSG_v7svNUd3880_fyUzfQDuRLJVTz6kUVNrzRImFFTCzYKFs" id="hero-img" alt="Vista aérea do município de Breves, Marajó, Pará" class="city-hero-img">

            <span class="badge"><i class="fas fa-star" aria-hidden="true"></i> Em Destaque</span>
            <h2 id="home-title" class="title-highlight">Zelando pelos direitos da criança e do adolescente</h2>
            <p class="text-spacing">O Conselho Tutelar é um órgão permanente e autônomo, encarregado pela sociedade de zelar pelo cumprimento dos direitos da criança e do adolescente no município de Breves e região do Marajó.</p>
        </section>

        <!-- SEÇÃO: SERVIÇOS AO CIDADÃO -->
        <section id="servicos" class="content-section" aria-labelledby="servicos-title">
            <h2 id="servicos-title" class="title-highlight">Serviços ao Cidadão</h2>
            <p class="text-spacing">Conheça os principais atendimentos e providências de competência do Conselho Tutelar prestados à comunidade:</p>
            
            <ul class="services-list">
                <li>
                    <i class="fas fa-circle-check" aria-hidden="true"></i>
                    <span><strong>Denúncia de violação de direitos:</strong> Atendimento a ocorrências de abuso, maus-tratos, exploração e negligência.</span>
                </li>
                <li>
                    <i class="fas fa-circle-check" aria-hidden="true"></i>
                    <span><strong>Requisição de documentos:</strong> Apoio na obtenção de segunda via de certidão de nascimento para crianças e adolescentes.</span>
                </li>
                <li>
                    <i class="fas fa-circle-check" aria-hidden="true"></i>
                    <span><strong>Encaminhamentos institucionais:</strong> Articulação para acesso à rede de saúde, assistência social e vagas em escolas/creches.</span>
                </li>
                <li>
                    <i class="fas fa-circle-check" aria-hidden="true"></i>
                    <span><strong>Acompanhamento de medidas:</strong> Monitoramento contínuo de medidas protetivas aplicadas.</span>
                </li>
                <li>
                    <i class="fas fa-circle-check" aria-hidden="true"></i>
                    <span><strong>Orientação jurídica e social:</strong> Suporte informativo e direcionamento adequado às famílias.</span>
                </li>
            </ul>
        </section>

        <!-- SEÇÃO: ECA -->
        <section id="eca" class="content-section" aria-labelledby="eca-title">
            <h2 id="eca-title" class="title-highlight">Estatuto da Criança e do Adolescente</h2>
            <p class="text-spacing">O marco legal que reúne as leis para a proteção integral de crianças e adolescentes no Brasil.</p>
            <div class="law-box">
                <h3 id="law-title">Carregando informações...</h3>
                <p id="law-text" class="law-text">Sincronizando com a base de dados do ECA.</p>
                <div class="law-controls">
                    <button class="law-btn" id="prev-law" aria-label="Artigo Anterior"><i class="fas fa-arrow-left" aria-hidden="true"></i> Anterior</button>
                    <button class="law-btn" id="next-law" aria-label="Próximo Artigo">Próximo <i class="fas fa-arrow-right" aria-hidden="true"></i></button>
                </div>
            </div>
        </section>

        <!-- SEÇÃO: NOTÍCIAS -->
        <section id="noticias" class="content-section" aria-labelledby="noticias-title">
            <h2 id="noticias-title" class="title-highlight" style="margin-bottom: 25px;">Últimas Atualizações</h2>
            <div class="news-grid" id="news-container">
                <p style="color:var(--text-muted); font-size:14px;">Carregando feed de notícias em tempo real...</p>
            </div>
        </section>

        <!-- SEÇÃO: CONSELHEIROS E PLANTÃO -->
        <section id="conselheiros" class="content-section" aria-labelledby="conselheiros-title">
            <div class="duty-box">
                <div class="duty-title">
                    <span><i class="fas fa-clock fa-lg" aria-hidden="true"></i> ESCALA DE PLANTÃO 24H</span>
                    <span style="background: rgba(16, 185, 129, 0.15); color: var(--success); padding: 4px 10px; border-radius: 12px; font-size: 11px; font-weight: 700;">ON-LINE</span>
                </div>
                <div class="duty-person">
                    <span id="duty-day"><strong>Carregando...</strong></span>
                    <span style="color: #b45309; font-weight: 600; font-size: 13px;"><i class="fas fa-sun" aria-hidden="true"></i> Dia (<span id="time-duty-day">08h às 18h</span>)</span>
                </div>
                <div class="duty-person">
                    <span id="duty-night"><strong>Carregando...</strong></span>
                    <span style="color: #4338ca; font-weight: 600; font-size: 13px;"><i class="fas fa-moon" aria-hidden="true"></i> Noite (<span id="time-duty-night">18h às 08h</span>)</span>
                </div>
            </div>

            <h2 id="conselheiros-title" class="title-highlight" style="font-size: 22px; margin-bottom: 15px;">Conselheiros Titulares</h2>
            <div class="staff-list">
                <div class="staff-card"><div class="avatar"><i class="fas fa-user-tie" aria-hidden="true"></i></div><div class="staff-info"><strong id="c-name-1">Reginaldo Moraes</strong><span class="staff-role">Coordenador Geral</span></div></div>
                <div class="staff-card"><div class="avatar"><i class="fas fa-user" aria-hidden="true"></i></div><div class="staff-info"><strong id="c-name-2">Sinara Duarte</strong><span class="staff-role">Conselheira Titular</span></div></div>
                <div class="staff-card"><div class="avatar"><i class="fas fa-user" aria-hidden="true"></i></div><div class="staff-info"><strong id="c-name-3">Elian Santos</strong><span class="staff-role">Conselheiro Titular</span></div></div>
                <div class="staff-card"><div class="avatar"><i class="fas fa-user" aria-hidden="true"></i></div><div class="staff-info"><strong id="c-name-4">Maria Joana Silva</strong><span class="staff-role">Conselheira Titular</span></div></div>
                <div class="staff-card"><div class="avatar"><i class="fas fa-user" aria-hidden="true"></i></div><div class="staff-info"><strong id="c-name-5">Carlos Mendes</strong><span class="staff-role">Conselheiro Titular</span></div></div>
            </div>
        </section>

        <!-- SEÇÃO: ADMINISTRAÇÃO -->
        <section id="admin" class="content-section" aria-labelledby="admin-title">
            <h2 id="admin-title" class="title-highlight" style="margin-bottom: 25px;"><i class="fas fa-cogs" style="font-size: 24px; color: var(--secondary);" aria-hidden="true"></i> Painel do Gestor</h2>
            
            <!-- TELA DE LOGIN -->
            <div id="admin-login-area" class="admin-card">
                <p style="margin-bottom: 15px; font-size: 14px;">Área restrita. Faça login com suas credenciais do Firebase para continuar.</p>
                <form id="login-form" style="display: flex; gap: 10px; max-width: 450px; flex-direction: column;">
                    <label for="admin-email" class="sr-only">E-mail</label>
                    <input type="email" id="admin-email" class="admin-input" style="margin-bottom: 0;" placeholder="E-mail do administrador..." required>
                    <div style="display: flex; gap: 10px;">
                        <label for="admin-pass" class="sr-only">Senha</label>
                        <input type="password" id="admin-pass" class="admin-input" style="margin-bottom: 0;" placeholder="Sua senha..." required>
                        <button type="submit" id="btn-login-submit" class="admin-btn" style="width: auto;"><span>Entrar</span></button>
                    </div>
                </form>
            </div>

            <!-- TELA DO PAINEL -->
            <div id="admin-dashboard-area" style="display: none;">
                <div class="admin-card">
                    <h4><i class="fas fa-map-signs" aria-hidden="true"></i> Adicionar Nova Cidade ao Plantão Digital</h4>
                    <label class="admin-label" for="new-city-name">Nome da Cidade (Ex: Curralinho)</label>
                    <input type="text" id="new-city-name" class="admin-input" placeholder="Digite o nome do município">
                    
                    <label class="admin-label" for="new-city-number">WhatsApp (Apenas números, com DDD)</label>
                    <input type="text" id="new-city-number" class="admin-input" placeholder="Ex: 5591999999999">
                    
                    <button id="btn-add-city" class="admin-btn"><i class="fas fa-plus" aria-hidden="true"></i> Adicionar ao Menu Lateral</button>
                </div>

                <div class="admin-card">
                    <h4><i class="fas fa-newspaper" aria-hidden="true"></i> Publicar Nova Notícia</h4>
                    <label class="admin-label" for="new-news-title">Título da Publicação</label>
                    <input type="text" id="new-news-title" class="admin-input" placeholder="Ex: Ação Social nas Escolas de Breves">
                    
                    <label class="admin-label" for="new-news-desc">Resumo da Notícia</label>
                    <textarea id="new-news-desc" class="admin-input" style="height: 90px; resize: none;" placeholder="Digite o conteúdo aqui..."></textarea>
                    
                    <button id="btn-publish" class="admin-btn admin-btn-success"><i class="fas fa-check" aria-hidden="true"></i> Publicar no Portal (Firestore)</button>
                </div>

                <div class="admin-card">
                    <h4><i class="fas fa-image" aria-hidden="true"></i> Trocar Imagem da Página Inicial</h4>
                    <label class="admin-label" for="new-hero-input">Selecione uma nova foto de capa</label>
                    <input type="file" id="new-hero-input" accept="image/*" class="admin-input">
                    <button id="btn-update-hero" class="admin-btn"><i class="fas fa-upload" aria-hidden="true"></i> Atualizar Capa</button>
                </div>

                <div class="admin-card">
                    <h4><i class="fas fa-clock" aria-hidden="true"></i> Atualizar Escala de Plantão</h4>
                    
                    <div style="display: flex; gap: 10px; flex-wrap: wrap;">
                        <div style="flex: 1; min-width: 200px;">
                            <label class="admin-label" for="input-duty-day">Plantão Dia (Nomes)</label>
                            <input type="text" id="input-duty-day" class="admin-input" placeholder="Ex: Fernando Soares / Paloma Nogueira">
                        </div>
                        <div style="flex: 1; min-width: 200px;">
                            <label class="admin-label" for="input-time-day">Horário Plantão Dia</label>
                            <input type="text" id="input-time-day" class="admin-input" placeholder="Ex: 08h às 18h">
                        </div>
                    </div>
                    
                    <div style="display: flex; gap: 10px; flex-wrap: wrap;">
                        <div style="flex: 1; min-width: 200px;">
                            <label class="admin-label" for="input-duty-night">Plantão Noite (Nomes)</label>
                            <input type="text" id="input-duty-night" class="admin-input" placeholder="Ex: Joia Barbosa / Socorro Sarges">
                        </div>
                        <div style="flex: 1; min-width: 200px;">
                            <label class="admin-label" for="input-time-night">Horário Plantão Noite</label>
                            <input type="text" id="input-time-night" class="admin-input" placeholder="Ex: 18h às 08h">
                        </div>
                    </div>
                    
                    <button id="btn-update-duty" class="admin-btn"><i class="fas fa-save" aria-hidden="true"></i> Salvar Escala no Firestore</button>
                </div>

                <div class="admin-card">
                    <h4><i class="fas fa-users" aria-hidden="true"></i> Atualizar Membros da Equipe</h4>
                    <label class="admin-label" for="input-c-1">Coordenador Geral</label>
                    <input type="text" id="input-c-1" class="admin-input" placeholder="Nome atual: Reginaldo Moraes">
                    
                    <label class="admin-label" for="input-c-2">Conselheiros Titulares</label>
                    <input type="text" id="input-c-2" class="admin-input" placeholder="Conselheiro 2">
                    <input type="text" id="input-c-3" class="admin-input" placeholder="Conselheiro 3">
                    <input type="text" id="input-c-4" class="admin-input" placeholder="Conselheiro 4">
                    <input type="text" id="input-c-5" class="admin-input" placeholder="Conselheiro 5">
                    
                    <button id="btn-update-staff" class="admin-btn"><i class="fas fa-save" aria-hidden="true"></i> Atualizar Equipe</button>
                </div>
                
                <button id="btn-logout" class="admin-btn" style="background-color: var(--accent); margin-top: 15px;"><i class="fas fa-sign-out-alt" aria-hidden="true"></i> Sair do Painel</button>
            </div>
        </section>

    </main>

    <aside class="sidebar">
        <div class="widget">
            <h3 class="widget-title">Plantão Digital</h3>
            <label for="citySelect" class="sr-only">Selecione sua Cidade</label>
            <select class="select-field" id="citySelect">
                <option value="">-- Escolha seu município --</option>
            </select>
            <a href="#" id="waBtn" class="btn-wa" target="_blank" rel="noopener noreferrer"><i class="fab fa-whatsapp fa-lg" aria-hidden="true"></i> INICIAR ATENDIMENTO</a>
        </div>
        
        <div class="emergency-box">
            <p style="font-weight: 800; color: var(--accent); margin-bottom: 15px; font-size: 14px;">CANAIS DE EMERGÊNCIA</p>
            <a href="tel:100" class="btn-panic btn-primary-bg"><i class="fas fa-phone-alt" aria-hidden="true"></i> DISQUE 100</a>
            <a href="tel:190" class="btn-panic btn-accent-bg"><i class="fas fa-shield-alt" aria-hidden="true"></i> POLÍCIA MILITAR (190)</a>
        </div>

        <div class="widget">
            <h3 class="widget-title">Onde Estamos</h3>
            <div class="contact-info">
                <p><i class="fas fa-map-marker-alt" aria-hidden="true"></i> <span><strong>Endereço:</strong><br> Rua Mário Curica, 986, Centro, Breves - PA.</span></p>
                <p><i class="fas fa-clock" aria-hidden="true"></i> <span><strong>Atendimento presencial:</strong><br> Segunda a quinta-feira<br>08h às 18h.</span></p>
                <p><i class="fas fa-envelope" aria-hidden="true"></i> <span><strong>E-mail institucional:</strong><br> ctbreves@gmail.com</span></p>
            </div>
        </div>
    </aside>
</div>

<footer>
    <p>Projeto de Extensão Acadêmica UNIASSELVI - 2026<br><strong>Desenvolvido para fins educacionais.</strong></p>
</footer>

<!-- LÓGICA JAVASCRIPT / FIREBASE FIRESTORE -->
<script type="module">
    import { initializeApp } from "https://www.gstatic.com/firebasejs/10.4.0/firebase-app.js";
    import { getAuth, signInWithEmailAndPassword, signOut, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/10.4.0/firebase-auth.js";
    import { 
        getFirestore, 
        collection, 
        doc, 
        addDoc, 
        setDoc, 
        deleteDoc, 
        onSnapshot, 
        query, 
        orderBy 
    } from "https://www.gstatic.com/firebasejs/10.4.0/firebase-firestore.js";

    // ----------------------------------------------------
    // CONFIGURAÇÃO DO FIREBASE (Com suas credenciais reais)
    // ----------------------------------------------------
    const firebaseConfig = {
      apiKey: "AIzaSyCARvd7jVZC7Ztxe0PZ5qMHj-hgXuHZGp8",
      authDomain: "conselhotutelarbreves-e1ac3.firebaseapp.com",
      projectId: "conselhotutelarbreves-e1ac3",
      storageBucket: "conselhotutelarbreves-e1ac3.firebasestorage.app",
      messagingSenderId: "745884003967",
      appId: "1:745884003967:web:5360ea5ef5f80d8a30994a",
      measurementId: "G-ENGB612K2L"
    };

    let app, auth, db;
    let isFirebaseReady = false;

    try {
        app = initializeApp(firebaseConfig);
        auth = getAuth(app);
        db = getFirestore(app);
        isFirebaseReady = true;
    } catch (e) {
        console.warn("Erro ao inicializar o Firebase. Verifique as credenciais.", e);
    }

    // Estado da Aplicação
    window.currentUser = null;

    const defaultData = {
        heroImg: 'https://encrypted-tbn2.gstatic.com/licensed-image?q=tbn:ANd9GcQNApHxECZLFzOATIMu9NAeQfuQKcyuo-cSG_v7svNUd3880_fyUzfQDuRLJVTz6kUVNrzRImFFTCzYKFs',
        cities: [
            { name: 'Breves (Sede)', phone: '5591991119938' },
            { name: 'Conselho Nacional', phone: '5561996110100' }
        ],
        news: [
            {
                id: 'demo-1',
                title: 'Campanha Maio Laranja em Breves',
                desc: 'Ações nas escolas de Breves sobre o combate ao abuso infantil e conscientização da comunidade.',
                img: null,
                createdAt: Date.now()
            }
        ],
        duty: {
            dayPerson: 'Fernando Soares / Paloma Nogueira',
            dayTime: '08h às 18h',
            nightPerson: 'Joia Barbosa / Socorro Sarges',
            nightTime: '18h às 08h'
        },
        staff: [
            'Reginaldo Moraes',
            'Sinara Duarte',
            'Elian Santos',
            'Maria Joana Silva',
            'Carlos Mendes'
        ]
    };

    // Função Utilitária para Notificações Toast
    function showToast(message, type = 'success') {
        const container = document.getElementById('toast-container');
        const toast = document.createElement('div');
        toast.className = `toast ${type}`;
        
        let icon = type === 'success' ? '<i class="fas fa-check-circle" style="color:var(--success)" aria-hidden="true"></i>' : 
                   type === 'error' ? '<i class="fas fa-exclamation-circle" style="color:var(--accent)" aria-hidden="true"></i>' : 
                   '<i class="fas fa-info-circle" aria-hidden="true"></i>';
                   
        toast.innerHTML = `${icon} <span>${message}</span>`;
        container.appendChild(toast);
        
        setTimeout(() => toast.classList.add('show'), 10);
        setTimeout(() => {
            toast.classList.remove('show');
            setTimeout(() => toast.remove(), 300);
        }, 3500);
    }

    // ----------------------------------------------------
    // NAVEGAÇÃO SPA & ACESSIBILIDADE ARIA
    // ----------------------------------------------------
    const navLinks = document.querySelectorAll('.nav-link');
    const contentSections = document.querySelectorAll('.content-section');

    navLinks.forEach(link => {
        link.addEventListener('click', function() {
            navLinks.forEach(btn => {
                btn.classList.remove('active');
                btn.setAttribute('aria-selected', 'false');
                btn.removeAttribute('aria-current');
            });
            contentSections.forEach(section => section.classList.remove('active'));

            this.classList.add('active');
            this.setAttribute('aria-selected', 'true');
            this.setAttribute('aria-current', 'page');

            const targetId = this.getAttribute('data-target');
            const targetSection = document.getElementById(targetId);
            if (targetSection) {
                targetSection.classList.add('active');
            }

            if(window.innerWidth < 900) {
                window.scrollTo({ top: 180, behavior: 'smooth' });
            }
        });
    });

    // Carousel do Estatuto da Criança e do Adolescente (ECA)
    const info = [
        { t: "Art. 131 do ECA", d: "O Conselho Tutelar é órgão permanente e autônomo, não jurisdicional, encarregado pela sociedade de zelar pelo cumprimento dos direitos da criança e do adolescente." },
        { t: "Art. 4º do ECA", d: "É dever da família, da comunidade, da sociedade em geral e do poder público assegurar, com absoluta prioridade, a efetivação dos direitos referentes à vida e à saúde." },
        { t: "Art. 18-A do ECA", d: "A criança e o adolescente têm o direito de ser educados e cuidados sem o uso de castigo físico ou de tratamento cruel ou degradante." },
        { t: "Art. 70 do ECA", d: "É dever de todos prevenir a ocorrência de ameaça ou violação dos direitos da criança e do adolescente." }
    ];
    let idx = 0;

    function renderLaw(index) {
        const lawTitle = document.getElementById('law-title');
        const lawText = document.getElementById('law-text');
        if (!lawTitle || !lawText) return;
        lawText.style.opacity = '0';
        setTimeout(() => {
            lawTitle.innerText = info[index].t;
            lawText.innerText = info[index].d;
            lawText.style.opacity = '1';
        }, 200);
    }

    document.getElementById('next-law')?.addEventListener('click', () => {
        idx = (idx + 1) % info.length;
        renderLaw(idx);
    });

    document.getElementById('prev-law')?.addEventListener('click', () => {
        idx = (idx - 1 + info.length) % info.length;
        renderLaw(idx);
    });

    setInterval(() => {
        idx = (idx + 1) % info.length;
        renderLaw(idx);
    }, 9000);

    // ----------------------------------------------------
    // INTEGRAÇÃO DE DADOS EM TEMPO REAL (FIRESTORE)
    // ----------------------------------------------------
    function initRealtimeSync() {
        renderLaw(0);

        if (!isFirebaseReady) {
            renderCitiesLocal(defaultData.cities);
            renderNewsLocal(defaultData.news);
            renderDutyLocal(defaultData.duty);
            renderStaffLocal(defaultData.staff);
            showToast("Modo de demonstração offline", "warning");
            return;
        }

        // 1. Ouvir Notícias em Tempo Real
        const qNews = query(collection(db, "noticias"), orderBy("createdAt", "desc"));
        onSnapshot(qNews, (snapshot) => {
            const newsList = [];
            snapshot.forEach(docSnap => {
                newsList.push({ id: docSnap.id, ...docSnap.data() });
            });
            renderNewsFirestore(newsList);
        }, (error) => {
            console.error("Erro ao sincronizar notícias:", error);
            renderNewsLocal(defaultData.news);
        });

        // 2. Ouvir Cidades em Tempo Real
        onSnapshot(collection(db, "cidades"), (snapshot) => {
            const citiesList = [];
            snapshot.forEach(docSnap => {
                citiesList.push(docSnap.data());
            });
            renderCitiesLocal(citiesList.length > 0 ? citiesList : defaultData.cities);
        });

        // 3. Ouvir Escala de Plantão em Tempo Real
        onSnapshot(doc(db, "configuracoes", "plantao"), (docSnap) => {
            if (docSnap.exists()) {
                renderDutyLocal(docSnap.data());
            } else {
                renderDutyLocal(defaultData.duty);
            }
        });

        // 4. Ouvir Equipe de Conselheiros
        onSnapshot(doc(db, "configuracoes", "equipe"), (docSnap) => {
            if (docSnap.exists() && docSnap.data().membros) {
                renderStaffLocal(docSnap.data().membros);
            } else {
                renderStaffLocal(defaultData.staff);
            }
        });

        // 5. Imagem da Capa
        onSnapshot(doc(db, "configuracoes", "capa"), (docSnap) => {
            if (docSnap.exists() && docSnap.data().url) {
                document.getElementById('hero-img').src = docSnap.data().url;
            }
        });
    }

    // Funções de Renderização na Interface
    function renderCitiesLocal(cities) {
        const selectMenu = document.getElementById('citySelect');
        if (!selectMenu) return;
        selectMenu.innerHTML = '<option value="">-- Escolha seu município --</option>';
        cities.forEach(c => {
            const option = document.createElement('option');
            option.value = c.phone;
            option.text = c.name;
            selectMenu.appendChild(option);
        });
    }

    function renderNewsFirestore(newsList) {
        const container = document.getElementById('news-container');
        if (!container) return;
        container.innerHTML = '';

        if (!newsList || newsList.length === 0) {
            container.innerHTML = '<p style="color:var(--text-muted); font-size:14px;">Nenhuma notícia publicada no momento.</p>';
            return;
        }

        newsList.forEach(item => {
            const article = document.createElement('article');
            article.className = 'news-item';
            
            const imgHTML = item.img 
                ? `<div class="news-img" style="padding:0;"><img src="${item.img}" alt="${item.title}"></div>`
                : `<div class="news-img"><i class="fas fa-newspaper fa-3x" aria-hidden="true"></i></div>`;
            
            const deleteBtnHTML = window.currentUser 
                ? `<button class="delete-news-btn" onclick="deleteNewsItem('${item.id}')"><i class="fas fa-trash" aria-hidden="true"></i> Excluir</button>` 
                : '';

            article.innerHTML = `
                ${imgHTML}
                <div class="news-body">
                    <h4>${item.title}</h4>
                    <p>${item.desc}</p>
                </div>
                ${deleteBtnHTML}
            `;
            container.appendChild(article);
        });
    }

    function renderNewsLocal(newsList) {
        renderNewsFirestore(newsList);
    }

    function renderDutyLocal(duty) {
        if (!duty) return;
        document.getElementById('duty-day').innerHTML = `<strong>${duty.dayPerson || ''}</strong>`;
        document.getElementById('time-duty-day').innerText = duty.dayTime || '08h às 18h';
        document.getElementById('duty-night').innerHTML = `<strong>${duty.nightPerson || ''}</strong>`;
        document.getElementById('time-duty-night').innerText = duty.nightTime || '18h às 08h';
    }

    function renderStaffLocal(staff) {
        if (!staff) return;
        staff.forEach((name, i) => {
            const el = document.getElementById(`c-name-${i + 1}`);
            if (el) el.innerText = name;
        });
    }

    // Excluir Notícia (Global para acesso inline via botão)
    window.deleteNewsItem = async function(docId) {
        if (!window.currentUser) {
            showToast("Você precisa estar autenticado para excluir!", "error");
            return;
        }

        if (!confirm("Deseja realmente excluir esta publicação?")) return;

        try {
            if (isFirebaseReady) {
                await deleteDoc(doc(db, "noticias", docId));
                showToast("Notícia excluída do banco de dados!");
            }
        } catch (error) {
            console.error("Erro ao excluir:", error);
            showToast("Erro ao excluir publicação.", "error");
        }
    };

    // Atendimento WhatsApp
    document.getElementById('citySelect')?.addEventListener('change', function() {
        const waBtn = document.getElementById('waBtn');
        if(this.value) {
            const apenasNumeros = this.value.replace(/\D/g, ''); 
            waBtn.href = "https://wa.me/" + apenasNumeros;
            waBtn.style.display = "block";
        } else {
            waBtn.style.display = "none";
        }
    });

    // ----------------------------------------------------
    // AUTENTICAÇÃO SEGURA VIA FIREBASE AUTH
    // ----------------------------------------------------
    const loginForm = document.getElementById('login-form');
    const loginSubmitBtn = document.getElementById('btn-login-submit');

    loginForm?.addEventListener('submit', async (e) => {
        e.preventDefault();
        const email = document.getElementById('admin-email').value.trim();
        const pass = document.getElementById('admin-pass').value.trim();

        if (!isFirebaseReady) {
            showToast("Firebase não inicializado.", "warning");
            return;
        }

        loginSubmitBtn.disabled = true;
        loginSubmitBtn.innerHTML = '<span class="spinner"></span> Autenticando...';

        try {
            await signInWithEmailAndPassword(auth, email, pass);
            showToast('Sessão iniciada com sucesso!');
            document.getElementById('admin-email').value = '';
            document.getElementById('admin-pass').value = '';
        } catch (error) {
            showToast('E-mail ou senha incorretos.', 'error');
            console.error("Erro de Auth:", error.code);
        } finally {
            loginSubmitBtn.disabled = false;
            loginSubmitBtn.innerHTML = '<span>Entrar</span>';
        }
    });

    document.getElementById('btn-logout')?.addEventListener('click', () => {
        signOut(auth).then(() => showToast('Sessão encerrada com sucesso!'));
    });

    if (isFirebaseReady) {
        onAuthStateChanged(auth, (user) => {
            window.currentUser = user;
            updateAdminUI(user);
        });
    }

    function updateAdminUI(user) {
        const loginArea = document.getElementById('admin-login-area');
        const dashboardArea = document.getElementById('admin-dashboard-area');
        
        if (user) {
            if (loginArea) loginArea.style.display = 'none';
            if (dashboardArea) dashboardArea.style.display = 'block';
        } else {
            if (loginArea) loginArea.style.display = 'block';
            if (dashboardArea) dashboardArea.style.display = 'none';
        }
        const deleteButtons = document.querySelectorAll('.delete-news-btn');
        deleteButtons.forEach(btn => btn.style.display = user ? 'block' : 'none');
    }

    // ----------------------------------------------------
    // AÇÕES DO PAINEL GESTOR (GRAVAÇÃO NO FIRESTORE)
    // ----------------------------------------------------

    // 1. Adicionar Cidade
    document.getElementById('btn-add-city')?.addEventListener('click', async () => {
        const name = document.getElementById('new-city-name').value.trim();
        const phone = document.getElementById('new-city-number').value.trim();

        if(!name || !phone) {
            showToast("Preencha o nome do município e o número!", 'warning');
            return;
        }

        try {
            await addDoc(collection(db, "cidades"), { name, phone });
            showToast(`Cidade de ${name} adicionada com sucesso!`);
            document.getElementById('new-city-name').value = '';
            document.getElementById('new-city-number').value = '';
        } catch (e) {
            showToast("Erro ao salvar cidade.", "error");
        }
    });

    // 2. Publicar Notícia
    document.getElementById('btn-publish')?.addEventListener('click', async () => {
        const title = document.getElementById('new-news-title').value.trim();
        const desc = document.getElementById('new-news-desc').value.trim();

        if (!title || !desc) {
            showToast("Preencha o título e o resumo da notícia!", 'warning');
            return;
        }

        try {
            await addDoc(collection(db, "noticias"), {
                title,
                desc,
                img: null,
                createdAt: Date.now()
            });
            showToast("Notícia publicada no Portal!");
            document.getElementById('new-news-title').value = '';
            document.getElementById('new-news-desc').value = '';
        } catch (e) {
            showToast("Erro ao publicar notícia.", "error");
        }
    });

    // 3. Atualizar Imagem de Capa
    document.getElementById('btn-update-hero')?.addEventListener('click', () => {
        const file = document.getElementById('new-hero-input').files[0];
        if (file) {
            const reader = new FileReader();
            reader.onload = async (e) => {
                const newImgUrl = e.target.result;
                document.getElementById('hero-img').src = newImgUrl;

                await setDoc(doc(db, "configuracoes", "capa"), { url: newImgUrl });
                showToast('Foto da página inicial atualizada!');
                document.getElementById('new-hero-input').value = '';
            };
            reader.readAsDataURL(file);
        } else {
            showToast('Selecione uma imagem primeiro.', 'warning');
        }
    });

    // 4. Salvar Escala de Plantão
    document.getElementById('btn-update-duty')?.addEventListener('click', async () => {
        const dayPerson = document.getElementById('input-duty-day').value.trim();
        const dayTime = document.getElementById('input-time-day').value.trim();
        const nightPerson = document.getElementById('input-duty-night').value.trim();
        const nightTime = document.getElementById('input-time-night').value.trim();

        const payload = {};
        if (dayPerson) payload.dayPerson = dayPerson;
        if (dayTime) payload.dayTime = dayTime;
        if (nightPerson) payload.nightPerson = nightPerson;
        if (nightTime) payload.nightTime = nightTime;

        if (Object.keys(payload).length === 0) {
            showToast('Preencha ao menos um campo para atualizar.', 'warning');
            return;
        }

        try {
            await setDoc(doc(db, "configuracoes", "plantao"), payload, { merge: true });
            showToast('Escala de plantão atualizada no Firestore!');
            document.getElementById('input-duty-day').value = '';
            document.getElementById('input-time-day').value = '';
            document.getElementById('input-duty-night').value = '';
            document.getElementById('input-time-night').value = '';
        } catch (e) {
            showToast("Erro ao atualizar plantão.", "error");
        }
    });

    // 5. Salvar Quadro de Conselheiros
    document.getElementById('btn-update-staff')?.addEventListener('click', async () => {
        const newStaff = [...defaultData.staff];
        let modificou = false;

        for (let i = 1; i <= 5; i++) {
            const novoNome = document.getElementById(`input-c-${i}`).value.trim();
            if (novoNome) {
                newStaff[i - 1] = novoNome;
                modificou = true;
                document.getElementById(`input-c-${i}`).value = ''; 
            }
        }

        if (!modificou) {
            showToast('Preencha o nome de pelo menos um conselheiro.', 'warning');
            return;
        }

        try {
            await setDoc(doc(db, "configuracoes", "equipe"), { membros: newStaff });
            showToast('Quadro de equipe atualizado no Firestore!');
        } catch (e) {
            showToast("Erro ao atualizar equipe.", "error");
        }
    });

    // Inicialização da Aplicação
    document.addEventListener('DOMContentLoaded', initRealtimeSync);
</script>
</body>
</html>

