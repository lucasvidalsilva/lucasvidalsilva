<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lucas Vidal Silva - Data Engineer</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;600;700&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            background: linear-gradient(135deg, #0f0c29 0%, #302b63 50%, #24243e 100%);
            color: #e0e0e0;
            font-family: 'JetBrains Mono', monospace;
            padding: 40px 20px;
            min-height: 100vh;
        }
        
        .container {
            max-width: 900px;
            margin: 0 auto;
        }
        
        .header {
            margin-bottom: 50px;
            animation: fadeInDown 0.8s ease-out;
        }
        
        .terminal-prompt {
            color: #00ff88;
            font-size: 2.5em;
            font-weight: 700;
            margin-bottom: 15px;
            text-shadow: 0 0 20px rgba(0, 255, 136, 0.5);
        }
        
        .subtitle {
            font-size: 1.2em;
            color: #a0a0a0;
            margin-bottom: 30px;
        }
        
        .role {
            color: #00d4ff;
            font-weight: 600;
        }
        
        .code-block {
            background: rgba(0, 0, 0, 0.4);
            border: 1px solid rgba(0, 255, 136, 0.3);
            border-radius: 8px;
            padding: 25px;
            margin: 30px 0;
            position: relative;
            overflow: hidden;
            animation: slideInLeft 0.8s ease-out 0.2s both;
        }
        
        .code-block::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, transparent, #00ff88, transparent);
            animation: scan 3s infinite;
        }
        
        .code-block code {
            color: #e0e0e0;
            line-height: 1.8;
        }
        
        .keyword {
            color: #ff79c6;
        }
        
        .string {
            color: #00ff88;
        }
        
        .function {
            color: #00d4ff;
        }
        
        .section {
            margin: 50px 0;
            animation: fadeIn 0.8s ease-out;
        }
        
        .section-title {
            color: #00ff88;
            font-size: 1.8em;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .section-title::before {
            content: '~/';
            color: #00d4ff;
        }
        
        .divider {
            height: 2px;
            background: linear-gradient(90deg, transparent, #00ff88, transparent);
            margin: 40px 0;
            opacity: 0.3;
        }
        
        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            margin: 20px 0;
        }
        
        .tech-category {
            background: rgba(0, 0, 0, 0.3);
            border-left: 3px solid #00ff88;
            padding: 15px;
            border-radius: 5px;
            transition: all 0.3s ease;
        }
        
        .tech-category:hover {
            background: rgba(0, 255, 136, 0.1);
            transform: translateX(5px);
            border-left-color: #00d4ff;
        }
        
        .tech-category strong {
            color: #00d4ff;
            display: block;
            margin-bottom: 8px;
        }
        
        .quote {
            background: linear-gradient(135deg, rgba(0, 212, 255, 0.1) 0%, rgba(0, 255, 136, 0.1) 100%);
            border-left: 4px solid #00ff88;
            padding: 25px;
            margin: 30px 0;
            font-style: italic;
            font-size: 1.1em;
            color: #b0b0b0;
            border-radius: 5px;
            position: relative;
            animation: slideInRight 0.8s ease-out 0.4s both;
        }
        
        .quote::before {
            content: '"';
            position: absolute;
            top: 10px;
            left: 10px;
            font-size: 3em;
            color: rgba(0, 255, 136, 0.2);
            font-family: Georgia, serif;
        }
        
        .project-card {
            background: rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(0, 212, 255, 0.3);
            border-radius: 8px;
            padding: 20px;
            margin: 15px 0;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 212, 255, 0.1), transparent);
            transition: left 0.5s ease;
        }
        
        .project-card:hover::before {
            left: 100%;
        }
        
        .project-card:hover {
            border-color: #00ff88;
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 255, 136, 0.2);
        }
        
        .project-arrow {
            color: #00d4ff;
            margin-right: 10px;
            font-weight: bold;
        }
        
        .project-title {
            color: #00ff88;
            font-size: 1.2em;
            font-weight: 600;
            margin-bottom: 10px;
        }
        
        .project-title a {
            color: #00ff88;
            text-decoration: none;
            transition: color 0.3s ease;
        }
        
        .project-title a:hover {
            color: #00d4ff;
        }
        
        .project-tech {
            color: #a0a0a0;
            font-size: 0.9em;
            margin-bottom: 8px;
        }
        
        .project-tech code {
            background: rgba(0, 212, 255, 0.2);
            padding: 2px 8px;
            border-radius: 3px;
            color: #00d4ff;
            margin-right: 5px;
        }
        
        .project-desc {
            color: #c0c0c0;
            line-height: 1.6;
        }
        
        .connect-section {
            text-align: center;
            margin: 50px 0;
        }
        
        .connect-buttons {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin: 25px 0;
            flex-wrap: wrap;
        }
        
        .connect-buttons img {
            transition: all 0.3s ease;
            filter: brightness(0.9);
        }
        
        .connect-buttons img:hover {
            transform: translateY(-3px);
            filter: brightness(1.1);
        }
        
        .footer {
            text-align: center;
            margin-top: 60px;
            padding-top: 30px;
            border-top: 1px solid rgba(0, 255, 136, 0.2);
            color: #808080;
            font-size: 0.9em;
            animation: fadeIn 1s ease-out 0.6s both;
        }
        
        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }
        
        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }
        
        @keyframes slideInRight {
            from {
                opacity: 0;
                transform: translateX(30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }
        
        @keyframes scan {
            0% {
                left: -100%;
            }
            100% {
                left: 100%;
            }
        }
        
        @keyframes pulse {
            0%, 100% {
                opacity: 1;
            }
            50% {
                opacity: 0.5;
            }
        }
        
        .typing-cursor {
            animation: pulse 1s infinite;
            color: #00ff88;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <div class="terminal-prompt">$ whoami<span class="typing-cursor">_</span></div>
            <div class="subtitle">
                <span class="role">Engenheiro de Dados</span> · Explorador de possibilidades através dos dados
            </div>
        </div>
        
        <div class="code-block">
            <code>
<span class="keyword">class</span> <span class="function">DataExplorer</span>:<br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="keyword">def</span> <span class="function">__init__</span>(self):<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.role = <span class="string">"Data Engineer"</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.mindset = <span class="string">"Building value through data"</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;self.approach = <span class="string">"Learn → Build → Innovate"</span><br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;<span class="keyword">def</span> <span class="function">explore</span>(self):<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="keyword">return</span> [<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="string">"Data Engineer"</span>,<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="string">"Machine Learning"</span>,<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="string">"Data Analytics"</span><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;]
            </code>
        </div>
        
        <div class="divider"></div>
        
        <div class="section">
            <div class="section-title">current_stack</div>
            <div class="tech-grid">
                <div class="tech-category">
                    <strong>Core</strong>
                    Python · SQL · Spark
                </div>
                <div class="tech-category">
                    <strong>Cloud & Infra</strong>
                    GCP · Docker · Airflow
                </div>
                <div class="tech-category">
                    <strong>Data & ML</strong>
                    Pandas · Scikit-learn · PySpark
                </div>
                <div class="tech-category">
                    <strong>Dev</strong>
                    FastAPI · PostgreSQL · Git
                </div>
            </div>
        </div>
        
        <div class="divider"></div>
        
        <div class="section">
            <div class="section-title">philosophy</div>
            <div class="quote">
                Dados isolados informam. Dados conectados revelam padrões. Dados aplicados geram impacto.
            </div>
            <p style="color: #c0c0c0; line-height: 1.8;">
                Acredito que a melhor forma de aprender é construindo. Por isso meus repositórios variam de pipelines de dados a experimentos de ML, passando por análises exploratórias e backends. Alguns projetos estão completos, outros em evolução, porém todos fazem parte da jornada.
            </p>
        </div>
        
        <div class="divider"></div>
        
        <div class="section">
            <div class="section-title">featured_work</div>
            
            <div class="project-card">
                <div class="project-title">
                    <span class="project-arrow">→</span>
                    <a href="https://github.com/lucasvidalsilva/vibify" target="_blank">Vibify</a>
                </div>
                <div class="project-tech">
                    <code>Scikit-learn</code>
                    <code>Pandas</code>
                </div>
                <div class="project-desc">
                    ETL automatizado para análise de vendas
                </div>
            </div>
            
            <div class="project-card">
                <div class="project-title">
                    <span class="project-arrow">→</span>
                    <a href="https://github.com/lucasvidalsilva/o-guardiao" target="_blank">O Guardião</a>
                </div>
                <div class="project-tech">
                    <code>Python</code>
                    <code>Parquet</code>
                    <code>Gemini</code>
                </div>
                <div class="project-desc">
                    Integração com Gemini: extração, análise e IA contra Golpes Digitais
                </div>
            </div>
            
            <div class="project-card">
                <div class="project-title">
                    <span class="project-arrow">→</span>
                    <a href="#" target="_blank">Cripto Analise</a>
                </div>
                <div class="project-tech">
                    <code>DBT</code>
                    <code>Streamlit</code>
                    <code>OpenAI API</code>
                </div>
                <div class="project-desc">
                    Extração de dados sobre Criptomoeda e Data App de Análise Cripto
                </div>
            </div>
        </div>
        
        <div class="divider"></div>
        
        <div class="section connect-section">
            <div class="section-title" style="justify-content: center;">lets_connect</div>
            <p style="color: #c0c0c0; margin-bottom: 20px;">
                Sempre aberto para trocar ideias sobre dados, arquitetura, ML ou qualquer projeto interessante.
            </p>
            <div class="connect-buttons">
                <a href="https://www.linkedin.com/in/lucas-vidal-silva-902034361/" target="_blank">
                    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn">
                </a>
                <a href="mailto:lucasvidalsilvah@gmail.com">
                    <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email">
                </a>
            </div>
        </div>
        
        <div class="footer">
            Construindo o futuro, um pipeline de cada vez.
        </div>
    </div>
</body>
</html>
