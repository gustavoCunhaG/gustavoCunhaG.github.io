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

    <script src="script.js"></script>
</body>
</html>



