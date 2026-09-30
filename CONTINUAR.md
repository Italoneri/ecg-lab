# ECG Lab — roteiro para continuar numa nova conversa

## 1. O que colar no início da nova conversa

Anexe o `index.html` (o app atual) e cole o texto abaixo. Não precisa anexar o `data/ptbxl.js`, a não ser que o pedido envolva os casos reais.

> Estou desenvolvendo o ECG Lab, um app gratuito para estudar ECG, para colegas de profissão. Anexei o index.html com o estado atual. Resumo do que já existe e das decisões tomadas está abaixo. Quero continuar a partir daqui, sem refazer o que já funciona.
>
> **Estrutura técnica:** `index.html` único, sem servidor, JavaScript puro (sem framework), desenho em canvas com papel milimetrado real (25 mm/s, 10 mm/mV). Ao lado dele, `data/ptbxl.js` com 300 ECGs reais do PTB-XL (define `window.ECGLAB_PACK`; sinais em int16 µV, delta por derivação, bytes separados em planos, zlib, base64). O app carrega esse arquivo por `<script>` (funciona no GitHub Pages e abrindo o arquivo direto), descompacta com `DecompressionStream` e guarda no IndexedDB; a constante `PACK_V` no index.html controla a versão (mudar o valor força o recarregamento). Bibliotecas externas: fontes do Google e JSZip do cdnjs (só para importar/exportar .zip). Progresso em localStorage.
>
> **Zoom:** componente genérico `ZoomView` usado em todos os traçados (papel, ECG normal, achados, simulados, casos reais). A área mantém a altura; o zoom redesenha o canvas mais nítido dentro dela. Botões + e −, controle deslizante, pinça, dois toques, Ctrl + roda; arrastar move. O compasso dos casos reais e os marcadores A/B do papel continuam funcionando com zoom. A tela cheia dos casos reais tem zoom próprio.
>
> **Idiomas:** botão PT | ES no topo. Textos no objeto `UI` (pt/es) e nos dados bilíngues (`GAL`, `PARTS`, `DEMO_INFO`, tabelas `T`, `QL`, `AXOPT`, `AXFULL`). Elementos estáticos usam `data-t`, `data-th` e `data-ta`. Em espanhol: "lpm", derivações DI/DII/DIII, tratamento por "tú".
>
> **Abas:** Aprender (Papel, ECG normal, Achados com 26 achados), Simulados (26 achados gerados por código), Casos reais (300 ECGs do PTB-XL em 31 diagnósticos + 4 de demonstração; sessões de 10 questões, compasso, tela cheia, atalhos de teclado). Importar/exportar ficam em "Opções avançadas".
>
> **Decisões:** nada de IA em tempo real no app (custo zero); casos reais só de bancos Open Access do PhysioNet, com crédito às fontes; ferramenta de estudo, não de diagnóstico.

## 2. Próximos passos (em ordem)

1. **Publicar no GitHub Pages** (seção 3).
2. ~~Embutir casos reais do PTB-XL~~ — feito: `data/ptbxl.js` com 300 ECGs.
3. **Outros bancos Open Access do PhysioNet:** LUDB (200 ECGs com início e fim das ondas marcados: exercícios de medir PR, QRS e QT com gabarito), Brugada-HUCA, Norwegian Endurance Athlete ECG, CU Ventricular Tachyarrhythmia.
4. **Modo expert:** vários achados no mesmo ECG, com correção item a item, e anotação com caneta.
5. **Revisão clínica:** um colega revisa os textos da galeria e as traduções dos laudos, nas duas línguas.

## 3. Como publicar no GitHub Pages (grátis)

1. Crie uma conta em github.com, se ainda não tiver.
2. Clique em **New repository**. Nome sugerido: `ecg-lab`. Marque **Public**. Clique em **Create repository**.
3. Na página do repositório, clique em **uploading an existing file** (ou **Add file → Upload files**). Arraste **o conteúdo da pasta ecg-lab**: `index.html`, `README.md` e a pasta `data` inteira (o GitHub mantém a pasta). Clique em **Commit changes**.
4. Confira se aparece `data/ptbxl.js` na lista de arquivos do repositório.
5. Vá em **Settings → Pages**. Em **Source**, escolha **Deploy from a branch**; em **Branch**, escolha `main` e a pasta `/ (root)`. Clique em **Save**.
6. Em 1 ou 2 minutos, o endereço aparece no topo dessa página, no formato `https://SEU-USUARIO.github.io/ecg-lab/`. É esse link que você compartilha.
7. Para atualizar o app depois: repita o passo 3 só com o `index.html` novo. A pasta `data` só precisa ser enviada de novo se os casos mudarem.

**Dica para o celular:** abrindo o link no navegador do celular, use "Adicionar à tela inicial" para o app aparecer como um ícone.

## 4. Observações

- Quem abre o link não precisa fazer nada: os 300 casos carregam sozinhos na primeira visita (cerca de 8 MB) e ficam guardados no navegador.
- Mantenha a seção de créditos às bases (exigência das licenças CC BY e ODC-By).
