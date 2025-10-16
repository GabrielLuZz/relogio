# Relógio Analógico

## Português

### Sobre
Este projeto é um relógio analógico simples com exibição digital, desenvolvido apenas com HTML, CSS e JavaScript. Ele mostra a hora atual utilizando três ponteiros (horas, minutos e segundos) e um visor digital abaixo do relógio.

### Funcionalidades
- Relógio analógico de 12 horas com ponteiros de horas, minutos e segundos
- Visor digital (HH:MM:SS) atualizado a cada segundo
- Marcas de hora a cada 30° (12 marcações)
- Layout centralizado na página

### Tecnologias utilizadas
- HTML5
- CSS3
- JavaScript (DOM API, `setInterval`, `Date`)

### Estrutura do projeto
```
/home/gabriel/dloa/relogio/
├── index.html
├── script.js
└── style.css
```

### Como executar
1. Baixe/clonar este projeto.
2. Abra o arquivo `index.html` diretamente no seu navegador.
   - Alternativamente, você pode servir a pasta com um servidor local:
     - Python: `python3 -m http.server` e acesse `http://localhost:8000/`
     - Node (http-server): `npx http-server .` e acesse a URL indicada

Não há dependências ou etapas de build; funciona em qualquer navegador moderno.

### Como funciona
- `index.html` define a estrutura do relógio (container, marcas, ponteiros e exibição digital).
- `style.css` estiliza o relógio, centraliza o layout e define tamanhos, cores e o comportamento de rotação via `transform-origin: left` para os ponteiros.
- `script.js` obtém a hora atual com `new Date()` e:
  - Atualiza o visor digital com `HH:MM:SS` (função `fixZero` adiciona zero à esquerda quando necessário)
  - Rotaciona os ponteiros usando graus calculados:
    - Segundos: `sDeg = (360 / 60) * second - 90`
    - Minutos: `mDeg = (360 / 60) * minute - 90`
    - Horas: `hDeg = (360 / 12) * hour - 90`
  - O deslocamento `-90` posiciona os ponteiros alinhados ao topo do relógio (considerando a origem de transformação à esquerda do elemento).
  - A atualização ocorre a cada 1000 ms via `setInterval(updateClock, 1000)`.

### Personalização
- Tamanhos e cores dos ponteiros podem ser ajustados em `style.css` (`.p_s`, `.p_m`, `.p_h`).
- O tamanho do relógio pode ser alterado em `.relogio` (`width`/`height`).
- Você pode adicionar mais marcações (por exemplo, a cada 5 minutos) duplicando elementos `.risco` no `index.html` e ajustando os ângulos.

### Limitações e melhorias sugeridas
- Ponteiro de horas não considera a fração dos minutos. Uma versão mais precisa pode usar:
  - `hDeg = (360 / 12) * hour + (360 / 12) * (minute / 60) - 90`
- Tornar o relógio responsivo (usar unidades relativas ao invés de valores fixos).
- Acessibilidade: adicionar descrições ARIA para o relógio digital e analógico.
- Adicionar animação suave com `requestAnimationFrame` para o ponteiro de segundos.
- Adicionar tema claro/escuro.

### Créditos
O rodapé do projeto indica "Criado pela B7Web" como atribuição. Caso deseje, mantenha ou personalize esta referência conforme o contexto do seu uso.

### Licença
Nenhuma licença definida. Recomenda-se adicionar uma licença (por exemplo, MIT) conforme a sua necessidade.

---

## English

### About
This project is a simple analog clock with a digital display, built with plain HTML, CSS, and JavaScript. It shows the current time using three hands (hours, minutes, seconds) and a digital display below the clock.

### Features
- 12-hour analog clock with hour, minute, and second hands
- Digital display (HH:MM:SS) updated every second
- Hour marks every 30° (12 marks)
- Centered page layout

### Tech stack
- HTML5
- CSS3
- JavaScript (DOM API, `setInterval`, `Date`)

### Project structure
```
/home/gabriel/dloa/relogio/
├── index.html
├── script.js
└── style.css
```

### How to run
1. Download/clone this project.
2. Open the `index.html` file directly in your browser.
   - Alternatively, serve the folder with a local server:
     - Python: `python3 -m http.server` and visit `http://localhost:8000/`
     - Node (http-server): `npx http-server .` and visit the indicated URL

There are no dependencies or build steps; it works in any modern browser.

### How it works
- `index.html` defines the clock structure (container, marks, hands, and digital display).
- `style.css` styles the clock, centers the layout, sets sizes and colors, and uses `transform-origin: left` for hand rotation.
- `script.js` gets the current time using `new Date()` and:
  - Updates the digital display with `HH:MM:SS` (`fixZero` adds leading zeros when needed)
  - Rotates the hands using calculated degrees:
    - Seconds: `sDeg = (360 / 60) * second - 90`
    - Minutes: `mDeg = (360 / 60) * minute - 90`
    - Hours: `hDeg = (360 / 12) * hour - 90`
  - The `-90` offset aligns the hands to the top of the clock (considering the left transform origin).
  - The update occurs every 1000 ms via `setInterval(updateClock, 1000)`.

### Customization
- Adjust hand sizes and colors in `style.css` (`.p_s`, `.p_m`, `.p_h`).
- Change the clock size in `.relogio` (`width`/`height`).
- Add more marks (e.g., every 5 minutes) by duplicating `.risco` elements in `index.html` and setting appropriate angles.

### Limitations and suggested improvements
- The hour hand does not account for minute fraction. A more accurate version can use:
  - `hDeg = (360 / 12) * hour + (360 / 12) * (minute / 60) - 90`
- Make the clock responsive (use relative units instead of fixed values).
- Accessibility: add ARIA descriptions for the analog and digital clock.
- Add smooth animation with `requestAnimationFrame` for the second hand.
- Add light/dark theme.

### Credits
The project footer states "Criado pela B7Web" (Created by B7Web). Keep or customize this attribution to suit your usage context.

### License
No license defined. Consider adding a license (e.g., MIT) according to your needs.