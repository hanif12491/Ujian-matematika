<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Admin - Bank Soal</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        .hidden-view { display: none !important; }
        table.custom-table { border-collapse: collapse; width: 100%; margin-top: 10px; margin-bottom: 10px; }
        table.custom-table th, table.custom-table td { border: 1px solid #cbd5e1; padding: 8px 12px; text-align: left; }
        table.custom-table th { background-color: #f1f5f9; }
    </style>
</head>
<body class="bg-gray-100 font-sans text-gray-800">

    <nav class="bg-blue-600 text-white p-4 shadow-md flex justify-between items-center">
        <h1 class="text-xl font-bold" id="exam-title-header">Kelola Bank Soal Ujian</h1>
        <a href="ujian.php" class="bg-white text-blue-600 px-4 py-2 rounded text-sm font-bold hover:bg-blue-50">← Kembali ke Ujian</a>
    </nav>

    <div class="container mx-auto p-6 max-w-4xl">
        <div class="bg-white p-6 rounded-lg shadow mb-6">
            <h3 class="font-bold text-green-700 mb-3 text-lg">➕ Tambah / Edit Soal Ujian</h3>
            <form onsubmit="handleSaveQuestion(event)">
                <div class="mb-3">
                    <label class="block font-semibold text-sm mb-1">Tipe Soal</label>
                    <select id="q-type" onchange="renderOptionsInput()" class="w-full px-3 py-2 border rounded bg-white text-sm">
                        <option value="pg">Pilihan Ganda</option>
                        <option value="pgm">Pilihan Ganda Majemuk</option>
                        <option value="bs">Benar - Salah</option>
                    </select>
                </div>
                <div class="mb-3">
                    <label class="block font-semibold text-sm mb-1">Pertanyaan / Soal</label>
                    <div class="flex gap-1 mb-2 bg-gray-50 p-2 border rounded text-xs">
                        <button type="button" onclick="insertSymbol('*')" class="px-2 py-1 bg-white border rounded font-mono font-bold text-blue-600">* (×)</button>
                        <button type="button" onclick="insertSymbol('^')" class="px-2 py-1 bg-white border rounded font-mono font-bold text-blue-600">^ (pangkat)</button>
                        <button type="button" onclick="insertSymbol('√')" class="px-2 py-1 bg-white border rounded font-mono">√</button>
                        <button type="button" onclick="insertSymbol('π')" class="px-2 py-1 bg-white border rounded font-mono">π</button>
                    </div>
                    <textarea id="q-text" rows="3" class="w-full px-3 py-2 border rounded text-sm font-mono" placeholder="Ketik soal..." required></textarea>
                </div>

                <div id="options-wrapper" class="space-y-2 mb-4"></div>

                <button type="submit" class="w-full bg-green-600 text-white font-bold py-2 rounded hover:bg-green-700 transition text-sm">SIMPAN SOAL</button>
            </form>
        </div>

        <h3 class="font-bold text-lg mb-3">Daftar Soal Terdaftar (<span id="q-count">0</span>)</h3>
        <div id="questions-list" class="space-y-3"></div>
    </div>

    <script>
        const urlParams = new URLSearchParams(window.location.search);
        const examId = parseInt(urlParams.get('id')) || 1;

        let examsDB = JSON.parse(localStorage.getItem('cbt_exams_db')) || [];
        let currentExam = examsDB.find(e => e.id === examId) || { title: "Ujian Default", questions: [] };

        document.getElementById('exam-title-header').innerText = `Kelola Soal: ${currentExam.title}`;

        function renderOptionsInput() {
            const type = document.getElementById('q-type').value;
            const wrapper = document.getElementById('options-wrapper');
            wrapper.innerHTML = '';

            if(type === 'pg') {
                let html = `<label class="block font-semibold text-sm mb-1">Pilihan Jawaban (A-E)</label>`;
                ['A','B','C','D','E'].forEach((lbl, idx) => {
                    html += `<div class="flex gap-2 items-center mb-1"><span class="font-bold">${lbl}.</span><input type="text" id="opt-${idx}" class="flex-1 px-3 py-1 border rounded text-sm" required></div>`;
                });
                html += `<div class="mt-2"><label class="block font-semibold text-sm mb-1">Kunci Jawaban Benar</label><select id="correct-pg" class="w-full px-3 py-2 border rounded text-sm bg-white font-bold text-green-700"><option value="0">A</option><option value="1">B</option><option value="2">C</option><option value="3">D</option><option value="4">E</option></select></div>`;
                wrapper.innerHTML = html;
            }
        }

        function insertSymbol(sym) {
            const txt = document.getElementById('q-text');
            txt.value += sym;
            txt.focus();
        }

        function handleSaveQuestion(e) {
            e.preventDefault();
            const text = document.getElementById('q-text').value;
            const type = document.getElementById('q-type').value;
            let options = [];
            let correct = 0;

            if(type === 'pg') {
                for(let i=0; i<5; i++) {
                    options.push({ text: document.getElementById(`opt-${i}`).value });
                }
                correct = parseInt(document.getElementById('correct-pg').value);
            }

            currentExam.questions.push({ id: Date.now(), type, text, options, correct });
            
            // Simpan ke localStorage
            const index = examsDB.findIndex(e => e.id === examId);
            if(index !== -1) examsDB[index] = currentExam;
            else examsDB.push(currentExam);
            
            localStorage.setItem('cbt_exams_db', JSON.stringify(examsDB));
            alert("Soal berhasil disimpan!");
            e.target.reset();
            renderQuestionsList();
            renderOptionsInput();
        }

        function renderQuestionsList() {
            const container = document.getElementById('questions-list');
            document.getElementById('q-count').innerText = currentExam.questions.length;
            container.innerHTML = '';
            
            currentExam.questions.forEach((q, idx) => {
                container.innerHTML += `
                    <div class="bg-white p-4 rounded border shadow-sm">
                        <span class="font-bold text-green-700 text-sm">Soal No. ${idx + 1}</span>
                        <p class="font-mono text-sm mt-1">${q.text}</p>
                    </div>
                `;
            });
        }

        renderOptionsInput();
        renderQuestionsList();
    </script>
</body>
</html>
