# ECG Lab

App gratuito para estudar eletrocardiograma, em português e espanhol.

- **Aprender:** papel milimetrado interativo, ECG normal anotado e galeria com 26 achados patológicos (critérios e traçado de exemplo).
- **Simulados:** traçados gerados na hora, com 4 alternativas e explicação.
- **Casos reais:** 300 ECGs reais de 12 derivações do PTB-XL (31 diagnósticos), em sessões de 10 questões, com zoom, compasso e tela cheia.

Todos os traçados têm zoom dentro da própria área: botões + e −, pinça com dois dedos, dois toques ou Ctrl + roda do mouse. Arraste para mover.

Funciona direto no navegador, sem servidor e sem cadastro. Os casos reais são carregados sozinhos na primeira visita e ficam guardados no aparelho, junto com o progresso.

## Arquivos

- `index.html` — o app.
- `data/ptbxl.js` — os 300 ECGs reais (cerca de 8 MB). Precisa ficar na pasta `data`, ao lado do `index.html`.

## Fontes dos traçados

- PTB-XL — Wagner et al., 2020. CC BY 4.0.
- PTB Diagnostic ECG Database — Bousseljot et al., 1995. ODC-By.
- MIT-BIH Arrhythmia Database — Moody e Mark, 2001. ODC-By.
- Todos disponíveis no PhysioNet (Goldberger et al., 2000).

Ferramenta de estudo. Não use para diagnóstico.
