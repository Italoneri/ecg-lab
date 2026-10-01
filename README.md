# ECG Lab

App gratuito para estudar eletrocardiograma, em português e espanhol.

- **Aprender:** papel milimetrado interativo, ECG normal anotado e galeria com 57 achados (critérios, nota clínica e traçado de exemplo).
- **Simulados:** 57 achados em 4 grupos (arritmias, condução e eixo, isquemia por parede, sobrecargas e outros), com 4 alternativas e explicação. Cada traçado mostra só as derivações que importam para o diagnóstico (por exemplo D2, D3, aVF e aVL no IAM inferior) e é gerado na hora por um modelo vetorial do coração: frequência, eixo, amplitudes, intervalos, subtipo e derivações mudam a cada vez, então o mesmo achado nunca sai igual. Os comuns respondem por cerca de 50% das perguntas, os menos comuns por 40% e os raros por 10%; achados errados voltam mais, e nenhum se repete nas 6 perguntas seguintes.
- **Casos reais:** 281 ECGs reais de 12 derivações do PTB-XL (30 diagnósticos), em sessões de 10 questões, com zoom, compasso e tela cheia.

Em cada questão e em cada achado da galeria há o botão **Reportar erro**. Ele abre um formulário do Google já preenchido com a seção, o caso ou achado, as respostas e um link que reabre exatamente aquele traçado (`#sim=achado.código`) ou caso real (`#caso=número`). Quem responde não precisa de conta Google.

Todos os traçados têm zoom dentro da própria área: botões + e −, pinça com dois dedos, dois toques ou Ctrl + roda do mouse. Arraste para mover.

Funciona direto no navegador, sem servidor e sem cadastro. Os casos reais são carregados sozinhos na primeira visita e ficam guardados no aparelho, junto com o progresso.

## Arquivos

- `index.html` — o app.
- `data/ptbxl.js` — os 281 ECGs reais (cerca de 7,5 MB). Precisa ficar na pasta `data`, ao lado do `index.html`.

## Como os casos reais foram escolhidos

Qualidade antes de quantidade. Só entram ECGs do PTB-XL que:

- têm laudo validado por cardiologista;
- têm o diagnóstico principal marcado como certo (100%), não como "possível";
- não têm ruído, deriva de linha de base nem problema de eletrodo registrados;
- passam numa conferência automática do traçado (frequência na taquicardia e bradicardia sinusal e no ECG normal, ritmo irregular na fibrilação atrial, eixo à esquerda no hemibloqueio anterior esquerdo).

A pergunta de eixo só aparece quando o eixo registrado na base e o eixo medido no traçado concordam, e a explicação mostra o eixo medido. Diagnósticos raros ficam com menos de 10 casos, e o infarto posterior ficou de fora por não ter nenhum caso com diagnóstico certo.

## Fontes dos traçados

- PTB-XL — Wagner et al., 2020. CC BY 4.0.
- PTB Diagnostic ECG Database — Bousseljot et al., 1995. ODC-By.
- MIT-BIH Arrhythmia Database — Moody e Mark, 2001. ODC-By.
- Todos disponíveis no PhysioNet (Goldberger et al., 2000).

Ferramenta de estudo. Não use para diagnóstico.
