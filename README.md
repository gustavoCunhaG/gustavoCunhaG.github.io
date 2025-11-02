# gustavoCunhaG.github.io
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Organizador de Sprints</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Meu Rastreador de Sprints</h1>
    </header>

    <main>
        <section class="form-container">
            <h2>Registrar Nova Sprint</h2>
            <form id="sprint-form">
                <div class="form-group">
                    <label for="sprint-name">Nome da Sprint:</label>
                    <input type="text" id="sprint-name" required>
                </div>
                <div class="form-group">
                    <label for="start-date">Data de Início:</label>
                    <input type="date" id="start-date" required>
                </div>
                <div class="form-group">
                    <label for="end-date">Data de Fim:</label>
                    <input type="date" id="end-date" required>
                </div>
                <div class="form-group">
                    <label for="sprint-tasks">Tarefas/Objetivos:</label>
                    <textarea id="sprint-tasks" rows="4"></textarea>
                </div>
                <button type="submit" class="btn">Adicionar Sprint</button>
            </form>
        </section>

        <hr>

        <section class="sprints-list">
            <h2>Sprints Registradas</h2>
            
            <div id="sprints-content">
                </div>

            <button id="export-pdf" class="btn btn-secondary">Exportar como PDF</button>
        </section>
    </main>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
    <style>
/* Reset básico e fontes */
    body {
        font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
        line-height: 1.6;
        background-color: #f4f7f6;
        color: #333;
        margin: 0;
        padding: 20px;
    }
    
    header {
        text-align: center;
        margin-bottom: 2rem;
        color: #2c3e50;
    }
    
    main {
        max-width: 900px;
        margin: 0 auto;
        background-color: #ffffff;
        padding: 2rem;
        border-radius: 8px;
        box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
    }
    
    /* Formulário */
    .form-container {
        margin-bottom: 2rem;
    }
    
    .form-group {
        margin-bottom: 1rem;
    }
    
    .form-group label {
        display: block;
        margin-bottom: 0.5rem;
        font-weight: 600;
    }
    
    .form-group input[type="text"],
    .form-group input[type="date"],
    .form-group textarea {
        width: 100%;
        padding: 0.75rem;
        border: 1px solid #ddd;
        border-radius: 5px;
        box-sizing: border-box; /* Garante que o padding não afete a largura */
    }
    
    .btn {
        display: inline-block;
        background-color: #3498db;
        color: #ffffff;
        padding: 0.75rem 1.5rem;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        font-size: 1rem;
        font-weight: 600;
        transition: background-color 0.3s ease;
    }
    
    .btn:hover {
        background-color: #2980b9;
    }
    
    .btn-secondary {
        background-color: #1abc9c;
    }
    
    .btn-secondary:hover {
        background-color: #16a085;
    }
    
    /* Lista de Sprints */
    .sprints-list h2 {
        border-bottom: 2px solid #eee;
        padding-bottom: 0.5rem;
    }
    
    .sprint-card {
        background-color: #fdfdfd;
        border: 1px solid #eaeaea;
        border-radius: 5px;
        padding: 1.5rem;
        margin-bottom: 1rem;
        box-shadow: 0 2px 5px rgba(0, 0, 0, 0.03);
    }
    
    .sprint-card h3 {
        margin-top: 0;
        color: #2c3e50;
    }
    
    .sprint-card p {
        margin-bottom: 0.5rem;
    }
    
    .sprint-card .dates {
        font-style: italic;
        color: #555;
        font-size: 0.9rem;
    }
    
    .sprint-card .tasks {
        white-space: pre-wrap; /* Preserva quebras de linha do textarea */
        background-color: #fafafa;
        padding: 1rem;
        border-radius: 4px;
        border: 1px dashed #ddd;
    }
    
    .sprint-card {
        /* Adiciona posicionamento relativo para o botão */
        position: relative; 
    }
    
    .btn-delete {
        position: absolute;
        top: 1rem;
        right: 1rem;
        background-color: #e74c3c; /* Vermelho */
        color: white;
        border: none;
        border-radius: 50%;
        width: 30px;
        height: 30px;
        cursor: pointer;
        font-weight: bold;
        font-size: 1rem;
        line-height: 30px; /* Centraliza o 'X' */
        text-align: center;
        transition: background-color 0.3s ease;
    }
    
    .btn-delete:hover {
        background-color: #c0392b; /* Vermelho mais escuro */
    }

</style>
    <script src="script.js"></script>
</body>
</html>



