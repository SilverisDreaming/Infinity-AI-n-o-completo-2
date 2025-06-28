# Infinity-AI-n-o-completo-2
código
# Infinity-AI-n-o-completo-
código
<!DOCTYPE HTML>

</html lang ="pt-br">

<head>

<meta charset ="UTF-8">

<meta name="viewport" content="width=device-width, intial scale=1.0">

<title> Infinite AI - By  Silver </title>

<style>
   * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #1a1a1a;
            color: #f0f0f0;
            line-height: 1.6;
        }

        header {
            background-color: #2b8597;
            color: #ffffff;
            padding: 15px 40px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
            flex-wrap: wrap;
        }

        .logo {
            font-size: 2.2em;
            font-weight: 700;
            color: #000000; 
            margin-right: 20px;
        }

        nav ul {
            list-style: none;
            margin: 0; /* Adicionado para garantir que não há margin padrão */
            padding: 0; /* Adicionado para garantir que não há padding padrão */
            display: flex;
            gap: 25px; /* Espaçamento entre os itens do menu */
            flex-wrap: wrap;
        }

        nav ul li a {
            color: #f4f4f4; /* Texto escuro para os links */
            text-decoration: none;
            padding: 8px 15px;
            border-radius: 6px;
            transition: background-color 0.3s ease, color 0.3s ease;
            font-weight: 600;
            white-space: nowrap; /* Impede quebras de linha em itens do menu */
        }

        nav ul li a:hover {
            background-color: rgba(255, 0, 0, 0.1); /* Um leve escurecimento */
            color: #e6bb76;
        }

        .auth-buttons {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
        }

        .auth-buttons button {
            background-color: #4CAF50; /* Verde para os botões de ação */
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 6px;
            cursor: pointer;
            font-size: 0.95em;
            font-weight: 600;
            transition: background-color 0.3s ease, transform 0.2s ease;
        }

        .auth-buttons button:hover {
            background-color: #7f48d7;
            transform: translateY(-2px);
        }

        main {
            padding: 30px 20px;
            max-width: 1200px;
            margin: 30px auto;
            display: grid; /* Usamos Grid para o layout principal */
            grid-template-columns: 1fr; /* Uma coluna por padrão */
            gap: 20px;
        }

        @media (min-width: 768px) {
            main {
                grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); /* Múltiplas colunas em telas maiores */
            }
        }

        .content-section {
            display: none; /* Oculta todas as seções por padrão */
            background-color: #333333; /* Fundo escuro para as seções */
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.4);
            grid-column: 1 / -1; /* Ocupa todas as colunas por padrão */
        }

        .content-section.active {
            display: block; /* Mostra a seção ativa */
        }
        
        /* Ajuste para seções específicas que podem ter layout diferente */
        #home-section,
        #profile-section,
        #signup-section,
        #signin-section {
            grid-column: 1 / -1; /* Ocupa a largura total */
        }


        h1 {
            color: #b4e6b6; /* Título em verde */
            border-bottom: 2px solid #555;
            padding-bottom: 15px;
            margin-bottom: 25px;
            font-size: 2.2em;
            text-align: center;
        }

        p {
            margin-bottom: 10px;
            color: #cccccc;
        }

        /* Histórico de Chats */
        .chat-list {
            display: flex;
            flex-direction: column;
            gap: 15px;
            margin-top: 20px;
        }

        .chat-item {
            background-color: #000000; /* Fundo mais claro para itens do chat */
            border: 1px solid #555;
            padding: 18px;
            border-radius: 8px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 10px;
            transition: transform 0.2s ease, background-color 0.2s ease;
        }

        .chat-item:hover {
            transform: translateY(-3px);
            background-color: #555555;
        }

        .chat-item p {
            margin: 0;
            font-weight: bold;
            color: #ffffff;
            font-size: 1.1em;
        }

        .chat-item span {
            font-size: 0.85em;
            color: #b0b0b0;
        }

        /* Perfil */
        .profile-details {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 15px;
            text-align: center;
        }

        .profile-pic {
           
            max: height 99px;
            width: 180px;
            height: 180px;
            border-radius: 50%;
            object-fit: cover;
            margin-bottom: 10px;
            border: 5px solid #4CAF50;
            box-shadow: 0 0 15px rgba(76, 175, 80, 0.5);
        }

        .profile-details p {
            margin: 0;
            font-size: 1.1em;
        }

        #btn-edit-profile {
            background-color: #3498db;
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 6px;
            cursor: pointer;
            margin-top: 20px;
            font-size: 1em;
            transition: background-color 0.3s ease, transform 0.2s ease;
        }

        #btn-edit-profile:hover {
            background-color: #2980b9;
            transform: translateY(-2px);
        }

        /* Modal de Edição de Perfil */
        .modal {
            display: none; /* Hidden by default */
            position: fixed; /* Stay in place */
            z-index: 1000; /* Sit on top */
            left: 0;
            top: 0;
            width: 100%; /* Full width */
            height: 100%; /* Full height */
            background-color: rgba(0,0,0,0.7); /* Black w/ more opacity */
            /* REMOVIDO: display: flex; justify-content: center; align-items: center; padding: 20px; */
            /* Estas propriedades devem ser aplicadas APENAS quando o modal estiver ATIVO */
            /* A classe 'active' do modal será controlada pelo JavaScript */
        }

        .modal.active { /* Nova regra para quando o modal está ativo */
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }


        .modal-content {
            background-color: #2a2a2a; /* Fundo escuro para o modal */
            padding: 30px;
            border: 1px solid #555;
            width: 90%;
            max-width: 600px;
            border-radius: 12px;
            position: relative;
            box-shadow: 0 8px 25px rgba(0,0,0,0.6);
            color: #f0f0f0;
        }

        .close-button {
            color: #aaa;
            position: absolute;
            top: 15px;
            right: 25px;
            font-size: 35px;
            font-weight: bold;
            cursor: pointer;
        }

        .close-button:hover,
        .close-button:focus {
            color: #ffffff;
        }

        .modal-content h2 {
            color: #4CAF50;
            margin-bottom: 20px;
            text-align: center;
        }

        .modal-content label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
            color: #f0f0f0;
        }

        .modal-content input[type="text"],
        .modal-content textarea {
            width: 100%;
            padding: 12px;
            margin-bottom: 20px;
            border: 1px solid #555;
            border-radius: 6px;
            background-color: #3a3a3a;
            color: #f0f0f0;
            font-size: 1em;
        }

        .modal-content textarea {
            resize: vertical;
            min-height: 100px;
        }

        #save-profile-changes {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 6px;
            cursor: pointer;
            margin-top: 10px;
            transition: background-color 0.3s ease, transform 0.2s ease;
            width: 100%;
            font-size: 1.1em;
        }

        #save-profile-changes:hover {
            background-color: #45a049;
            transform: translateY(-2px);
        }

        /* Formulários de Autenticação */
        .auth-section form {
            display: flex;
            flex-direction: column;
            max-width: 450px;
            margin: 20px auto;
            padding: 30px;
            border: 1px solid #555;
            border-radius: 10px;
            background-color: #2a2a2a;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.4);
        }

        .auth-section label {
            margin-top: 15px;
            margin-bottom: 8px;
            font-weight: bold;
            color: #f0f0f0;
        }

        .auth-section input[type="text"],
        .auth-section input[type="email"],
        .auth-section input[type="password"],
        .auth-section input[type="tel"] {
            padding: 12px;
            margin-bottom: 18px;
            border: 1px solid #555;
            border-radius: 6px;
            background-color: #3a3a3a;
            color: #f0f0f0;
            font-size: 1em;
        }

        .phone-verification {
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .phone-verification input[type="checkbox"] {
            transform: scale(1.2);
        }

        .phone-verification label {
            margin: 0;
            font-weight: normal;
            color: #f0f0f0;
        }

        .auth-section button[type="submit"] {
            background-color: #28a745; /* Verde para botões de submissão */
            color: white;
            border: none;
            padding: 14px 25px;
            border-radius: 6px;
            cursor: pointer;
            font-size: 1.15em;
            transition: background-color 0.3s ease, transform 0.2s ease;
            margin-top: 15px;
        }

        .auth-section button[type="submit"]:hover {
            background-color: #218838;
            transform: translateY(-2px);
        }

        .social-login {
            text-align: center;
            margin-top: 30px;
            padding: 0 20px;
        }

        .social-login p {
            margin-bottom: 15px;
            font-weight: bold;
            font-size: 1.1em;
            color: #f0f0f0;
        }

        .social-btn-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 12px;
        }

        .social-btn {
            color: white;
            border: none;
            padding: 12px 18px;
            border-radius: 6px;
            cursor: pointer;
            font-size: 0.95em;
            transition: opacity 0.3s ease, transform 0.2s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            min-width: 120px;
        }

        .social-btn:hover {
            opacity: 0.85;
            transform: translateY(-2px);
        }

        /* Cores específicas para botões sociais */
        .social-btn.google { background-color: #ea4335; }
        .social-btn.apple { background-color: #000000; }
        .social-btn.pc { background-color: #007bff; }
        .social-btn.instagram { background-color: #E1306C; }
        .social-btn.twitter { background-color: #1DA1F2; }
        .social-btn.reddit { background-color: #FF4500; }

        footer {
            text-align: center;
            padding: 25px;
            margin-top: 40px;
            background-color: #ff8c00; /* Laranja também no rodapé */
            color: #1a1a1a;
            box-shadow: 0 -4px 8px rgba(0,0,0,0.3);
            font-size: 0.9em;
            font-weight: 600;
        }

        /* Media Queries para Responsividade */
        @media (max-width: 768px) {
            header {
                flex-direction: column;
                padding: 15px 20px;
            }

            .logo {
                margin-bottom: 15px;
                margin-right: 0;
            }

            nav ul {
                flex-direction: column;
                align-items: center;
                gap: 10px;
                margin-bottom: 15px;
            }

            .auth-buttons {
                flex-direction: column;
                gap: 10px;
                width: 100%;
            }

            .auth-buttons button {
                width: 100%;
            }

            main {
                padding: 20px 15px;
                margin: 20px auto;
            }

            .content-section {
                padding: 20px;
            }

            h1 {
                font-size: 1.8em;
                margin-bottom: 20px;
            }

            .modal-content {
                width: 95%;
                padding: 20px;
            }

            .close-button {
                font-size: 30px;
                top: 10px;
                right: 20px;
            }
            .social-btn {
                width: 100%;
                min-width: unset;
            }
        }
    </style>
</head>
<body>

<header>
    <div class="logo">
        <img src="https://files.catbox.moe/277ok5.jpeg" 
        alt="Logo Infinity AI">
    </div>
    </header>
        <nav>
            <ul>
                <li><a href="#" id="nav-home">Início</a></li>
                <li><a href="#" id="nav-chat-history">Histórico de Chats</a></li>
                <li><a href="#" id="nav-profile">Perfil</a></li>
                <li><a href="#" id="nav-settings">Configurações</a></li>
                <li><a href="#" id="nav-followed">Pessoas que você segue</a></li>
                <li><a href="#" id="nav-my-characters">Meus personagens</a></li>
                <li><a href="#" id="nav-blocked-characters">Personagens bloqueados</a></li>
            </ul>
        </nav>
        <div class="auth-buttons">
            <button id="btn-login">Faça Login!</button>
            <button id="btn-existing-account">Entrar em uma conta existente</button>
        </div>
    </header>

    <main>
        <section id="home-section" class="content-section active">
            <h1>Bem-vindo ao Dream AI!</h1>
            <p>Explore um universo de chatbots interativos.</p>
        </section>

        <section id="chat-history-section" class="content-section">
            <h1>Histórico de Chats</h1>
            <div class="chat-list">
                <div class="chat-item">
                    <p>Conversa com *Maki Zenin*</p>
                    <span>Data: 02/06/2025 - Hora: 20:30</span>
                </div>
                <div class="chat-item">
                    <p>Conversa com *Satoru Gojo*</p>
                    <span>Data: 01/06/2025 - Hora: 18:00</span>
                </div>
            </div>
        </section>

        <section id="profile-section" class="content-section">
            <h1>Meu Perfil</h1>
            <div class="profile-details">
                <img src="https://via.placeholder.com/180/4CAF50/FFFFFF?text=Seu+Avatar" alt="Foto de Perfil" class="profile-pic">
                <p><strong>Nome:</strong> <span id="profile-name-display">Usuário Exemplo</span></p>
                <p><strong>Conta criada em:</strong> 01/01/2024</p>
                <p><strong>Descrição:</strong> <span id="profile-description-display">Olá, sou um usuário do Dream AI e adoro conversar com personagens interessantes!</span></p>
                <button id="btn-edit-profile">Editar Perfil</button>

                <div id="edit-profile-modal" class="modal">
                    <div class="modal-content">
                        <span class="close-button">&times;</span>
                        <h2>Editar Perfil</h2>
                        <label for="edit-name">Nome:</label>
                        <input type="text" id="edit-name" value="Usuário Exemplo">
                        <label for="edit-description">Descrição:</label>
                        <textarea id="edit-description">Olá, sou um usuário do Dream AI e adoro conversar com personagens interessantes!</textarea>
                        <label for="edit-photo">Foto de Perfil (URL):</label>
                        <input type="text" id="edit-photo" value="https://via.placeholder.com/180/4CAF50/FFFFFF?text=Seu+Avatar">
                        <button id="save-profile-changes">Salvar Alterações</button>
                    </div>
                </div>
            </div>
        </section>

        <section id="settings-section" class="content-section">
            <h1>Configurações</h1>
            <p>Opções de configuração do usuário (privacidade, notificações, etc.).</p>
        </section>

        <section id="followed-section" class="content-section">
            <h1>Pessoas que você segue</h1>
            <p>Lista de usuários ou criadores de personagens que você segue.</p>
        </section>

        <section id="my-characters-section" class="content-section">
            <h1>Meus Personagens</h1>
            <p>Aqui você poderá ver e gerenciar os chatbots que você criou.</p>
        </section>

        <section id="blocked-characters-section" class="content-section">
            <h1>Personagens Bloqueados</h1>
            <p>Lista de personagens que você bloqueou para não interagir.</p>
        </section>

        <section id="signup-section" class="content-section auth-section">
            <h1>Faça Login! (Crie sua conta)</h1>
            <form id="signup-form">
                <label for="signup-name">Nome:</label>
                <input type="text" id="signup-name" required>

                <label for="signup-email">Email:</label>
                <input type="email" id="signup-email" required>

                <label for="signup-password">Senha:</label>
                <input type="password" id="signup-password" required>

                <label for="signup-confirm-password">Confirme a Senha:</label>
                <input type="password" id="signup-confirm-password" required>

                <div class="phone-verification">
                    <input type="checkbox" id="signup-phone-verify">
                    <label for="signup-phone-verify">Verificar com número de telefone</label>
                    <input type="tel" id="signup-phone-number" placeholder="Ex: (XX) XXXXX-XXXX" style="display: none;">
                </div>

                <button type="submit">Criar Conta</button>
            </form>
        </section>

        <section id="signin-section" class="content-section auth-section">
            <h1>Entrar em uma conta existente</h1>
            <form id="signin-form">
                <label for="signin-email">Email:</label>
                <input type="email" id="signin-email" required>

                <label for="signin-password">Senha:</label>
                <input type="password" id="signin-password" required>

                <button type="submit">Entrar</button>
            </form>
            <div class="social-login">
                <p>Ou conecte com:</p>
                <div class="social-btn-container">
                    <button class="social-btn google">Google</button>
                    <button class="social-btn apple">Apple</button>
                    <button class="social-btn pc">PC (Exemplo)</button>
                    <button class="social-btn instagram">Instagram</button>
                    <button class="social-btn twitter">Twitter</button>
                    <button class="social-btn reddit">Reddit</button>
                </div>
            </div>
        </section>
    </main>

    <footer>
        <p>&copy; 2025 Dream AI. Todos os direitos reservados.</p>
    </footer>
   
   
    

/* Estilos para a seção de Bots */
#bots-section {
    grid-column: 1 / -1; /* Garante que a seção de bots ocupe toda a largura */
}

.bots-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); /* 280px é o tamanho mínimo do card */
    gap: 25px; /* Espaçamento entre os cards */
    margin-top: 20px;
    justify-content: center; /* Centraliza os cards quando não preenchem a largura total */
}

.bot-card {
    background-color: #2a2a2a; /* Fundo mais escuro para o card */
    border: 1px solid #444;
    border-radius: 12px;
    padding: 20px;
    text-align: center;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.4);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    cursor: pointer;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.bot-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.6);
}

.bot-card img {
    width: 120px;
    height: 120px;
    border-radius: 50%;
    object-fit: cover;
    margin-bottom: 15px;
    border: 3px solid #ff8c00; /* Borda laranja para o avatar do bot */
    box-shadow: 0 0 10px rgba(255, 140, 0, 0.5); /* Sombra laranja */
}

.bot-card h3 {
    color: #4CAF50; /* Título do bot em verde */
    font-size: 1.6em;
    margin-bottom: 8px;
}

.bot-card p {
    color: #cccccc;
    font-size: 0.95em;
    margin-bottom: 15px;
    flex-grow: 1; /* Permite que a descrição ocupe o espaço disponível */
}

.bot-card .creator-info {
    font-size: 0.85em;
    color: #999999;
    margin-top: 10px;
}

.bot-card .chat-button {
    background-color: #3498db; /* Botão de chat em azul */
    color: white;
    border: none;
    padding: 10px 20px;
    border-radius: 8px;
    cursor: pointer;
    font-size: 1em;
    font-weight: 600;
    margin-top: auto; /* Empurra o botão para o final do card */
    transition: background-color 0.3s ease, transform 0.2s ease;
}

.bot-card .chat-button:hover {
    background-color: #2980b9;
    transform: translateY(-2px);
}

/* Media Queries para Responsividade dos Bots */
@media (max-width: 600px) {
    .bots-grid {
        grid-template-columns: 1fr; /* Uma coluna em telas menores */
    }
}
