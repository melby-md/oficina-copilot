🌐 [Português (BR)](README.pt_BR.md) | [Español](README.es.md)

<!-- Hero -->
# Soc Ops — Social Bingo for Friendlier Mixers

Soc Ops transforma encontros presenciais em jogos sociais: um bingo de perguntas rápidas para quebrar o gelo, incentivar conversas e fazer conexões reais.

📍 Projetado para workshops, meetups e atividades de team building — simples de configurar e divertido de jogar.

📚 **Explore o guia do workshop:** [workshop/GUIDE.md](workshop/GUIDE.md)

---

**Por que usar Soc Ops?**

- **Rápido para iniciar:** roda com Java + Maven (ou o `mvnw` incluso).
- **Personalizável:** prompts de icebreakers editáveis em `socops/src/main/java/com/socops/data/IcebreakerPrompts.java`.
- **Pensado para facilitadores:** inclui material de workshop passo a passo em `workshop/`.
- **Código aberto:** fácil de estender para salas híbridas ou eventos maiores.

---

**Demonstração rápida**

1. Abra um terminal
2. Rode o backend Spring Boot:

```bash
cd socops
./mvnw spring-boot:run
```

3. Abra `http://localhost:8080` no navegador e comece a jogar.

---

**Conteúdo do repositório**

- **`socops/`**: aplicativo Spring Boot (backend, templates, assets).
- **`workshop/`**: material do lab dividido em passos (setup, design, quiz master, multi-agent).
- **`docs/`**: documentação e recursos visuais para apresentação.

---

**Como contribuir**

- Siga o [CONTRIBUTING.md](CONTRIBUTING.md) e abra PRs pequenas e focadas.
- Quer adicionar perguntas temáticas ao jogo? Envie uma PR com novos prompts.

---

**Recursos úteis**

- Guia completo do workshop: [workshop/GUIDE.md](workshop/GUIDE.md)
- Código principal: [socops/src/main/java/com/socops](socops/src/main/java/com/socops)

---

Licença: [LICENSE](LICENSE)

Se quiser, eu posso: atualizar também os READMEs em Português e Espanhol, ou gerar um screenshot/preview para a seção "Demonstração".
