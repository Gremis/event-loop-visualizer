# 🚀 JavaScript Event Loop Visualizer

<div align="center">

![Version](https://img.shields.io/badge/version-1.0.0-blue?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)
![Pure JavaScript](https://img.shields.io/badge/pure-vanilla%20JS-yellow?style=flat-square)
![No Dependencies](https://img.shields.io/badge/no-dependencies-brightgreen?style=flat-square)

**Uma visualização interativa e futurista que ensina como o JavaScript Event Loop realmente funciona.**

[📖 Documentação](#-como-funciona) • [🎮 Como Usar](#-como-usar) • [✨ Recursos](#-recursos) • [📸 Screenshots](#-screenshots)

</div>

---

## ✨ Recursos

- 🎯 **Visualização Completa do Event Loop** - Call Stack, Web APIs, Microtask Queue, Callback Queue
- 🎨 **Design Futurista Premium** - Interface escura com efeitos neon e glassmorphism
- ⚡ **Animações Suaves** - Transições elegantes e efeitos visuais profissionais
- 🎮 **Controles Interativos** - Pause, resume, reset e controle de velocidade
- 📊 **Timeline Detalhado** - Logs passo a passo do processo de execução
- 💻 **Console de Output** - Visualize o resultado da execução em tempo real
- 🎓 **Educacional** - Exemplos práticos de `setTimeout`, `Promise`, `fetch` e `async/await`
- 📱 **Responsivo** - Funciona perfeitamente em desktop para gravação
- ⚙️ **Sem Dependências** - HTML, CSS e JavaScript puro - nada mais!
- 🚀 **Offline** - Funciona completamente offline, basta abrir o arquivo

---

## 🎮 Como Usar

### Instalação

1. **Clone ou baixe este repositório**
```bash
git clone https://github.com/Gremis/event-loop-visualizer.git
cd event-loop-visualizer
```

2. **Abra o arquivo `index.html` no navegador**
   - Windows/Mac: Clique duas vezes em `index.html`
   - Linux: `open index.html` ou `xdg-open index.html`

Pronto! Nenhuma instalação ou compilação necessária.

### Controles

| Botão | Função |
|-------|--------|
| **Run setTimeout** | Visualiza comportamento de `setTimeout` |
| **Run Promise** | Mostra prioridade de microtasks vs callbacks |
| **Run Fetch** | Simula operação assíncrona de fetch |
| **Run Async/Await** | Demonstra async/await na prática |
| **Run Full Demo** | Executa cenário completo com todos os casos |
| **⏸ Pause** | Pausa a animação |
| **▶ Resume** | Retoma a execução |
| **↻ Reset** | Limpa tudo e volta ao estado inicial |

### Ajustes

- **🎚️ Slider de Velocidade**: 0.5x (mais lento) até 3x (mais rápido)
- **📈 Contador de Passos**: Mostra quantos passos foram executados
- **📍 Label de Fase**: Indica a fase atual (Idle, Execution, Microtask, etc)

---

## 📖 Como Funciona

### O Problema que Resolvemos

Entender o JavaScript Event Loop é desafiador! Este visualizador mostra:

1. **Por que `Promise` executa antes de `setTimeout`?**
   - Microtasks têm prioridade maior

2. **Como o Event Loop funciona?**
   - Monitora Call Stack e move tarefas quando vazio

3. **Qual é a diferença entre callbacks?**
   - Microtask Queue vs Callback Queue

4. **O que realmente acontece com `async/await`?**
   - Na verdade, são promises sob o capô

### Fluxo de Execução

```
Global Execution
    ↓
┌─────────────────────────────────────┐
│       CALL STACK                     │
│  (Executa código síncrono)          │
└─────────────────────────────────────┘
    ↓
┌─────────────────────────────────────┐
│  Async Operations → WEB APIs         │
│  (setTimeout, fetch, etc)            │
└─────────────────────────────────────┘
    ↓
EVENT LOOP verifica: Call Stack vazio?
    ↓
SIM → Drena MICROTASK QUEUE (Promises)
    ↓
SIM → Executa um item da CALLBACK QUEUE
    ↓
Volta ao início do EVENT LOOP
```

---

## 💡 Exemplos de Código Visualizados

### Exemplo 1: setTimeout vs Promise

```javascript
console.log("Start");

setTimeout(() => {
  console.log("Timeout");
}, 1000);

Promise.resolve().then(() => {
  console.log("Promise");
});

console.log("End");
```

**Output:**
```
Start
End
Promise
Timeout
```

**Por quê?**
1. `console.log("Start")` → executa imediatamente
2. `setTimeout` → vai para Web APIs (callback vai para Callback Queue)
3. `Promise.then()` → vai para Microtask Queue
4. `console.log("End")` → executa imediatamente
5. Call Stack vazio → Event Loop drena Microtask Queue
6. Microtask executa → `Promise` é impresso
7. Event Loop executa Callback Queue → `Timeout` é impresso

---

## 🎨 Design & Visual

### Componentes Visuais

- **Code Panel**: Código-fonte com realce de linha ativa
- **Call Stack**: Visualização em pilha com animações
- **Microtask Queue**: Fila prioritária (em roxo)
- **Callback Queue**: Fila normal (em rosa)
- **Web APIs**: Área de operações assíncronas
- **Event Loop**: Animação central com pulso e rotação
- **Timeline**: Logs detalhados passo a passo
- **Output Console**: Resultado da execução em tempo real

### Cores & Temas

- 🔵 **Cyan (#00d4ff)**: Call Stack, executando
- 🟣 **Purple (#b026ff)**: Microtasks, prioritário
- 🔴 **Pink (#ff006e)**: Callbacks, normal
- 🟢 **Green (#00ff88)**: Async operations
- 🟡 **Yellow (#ffb300)**: Números e constantes

---

## 🛠️ Tecnologia

- **HTML5** - Estrutura semântica
- **CSS3** - Estilos avançados, animações, glassmorphism
- **JavaScript ES6+** - Lógica e orquestração
- **Sem Frameworks** - Vanilla JavaScript puro
- **Sem Build Tools** - Funciona direto do navegador
- **Sem Dependências Externas** - Tudo incluído em um arquivo

---

## 📚 O que Você Aprenderá

Depois de interagir com este visualizador, você entenderá:

✅ Como o Call Stack funciona  
✅ O que são Web APIs  
✅ Diferença entre Microtask Queue e Callback Queue  
✅ Como o Event Loop prioriza tarefas  
✅ Por que `Promise.then()` executa antes de `setTimeout`  
✅ Como `async/await` funciona internamente  
✅ O que significa "non-blocking" em JavaScript  
✅ Como otimizar performance com essa compreensão  

---

## 🚀 Próximas Melhorias (Roadmap)

- [ ] Adicionar som/efeitos sonoros opcionais
- [ ] Modo escuro/claro
- [ ] Exportar gravação como GIF
- [ ] Mais exemplos de código
- [ ] Modo de aula interativa
- [ ] Dark mode animations mais complexas
- [ ] Suporte a múltiplas abas/janelas
- [ ] Tema personalizável

---

## 📄 Licença

Este projeto está sob a licença **MIT**. Sinta-se livre para usar, modificar e compartilhar!

```
MIT License

Copyright (c) 2024 Gremis

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

---

## 🙌 Contribuições

Sugestões e contribuições são bem-vindas! Sinta-se livre para:

- 🐛 Reportar bugs
- 💡 Sugerir novas features
- 🎨 Melhorar o design
- 📖 Corrigir documentação
- 🔧 Otimizar código

---

## 📧 Contato

Se você gostou deste projeto, considere:

- ⭐ Dar uma estrela no GitHub
- 🔗 Compartilhar com seus amigos desenvolvedores
- 📱 Marcar em suas redes sociais
- 💬 Enviar feedback e sugestões

---

<div align="center">

**Feito com ❤️ e JavaScript Vanilla**

Criado para ajudar desenvolvedores a entender o JavaScript Event Loop

[⬆ Voltar ao Topo](#-javascript-event-loop-visualizer)

</div>
