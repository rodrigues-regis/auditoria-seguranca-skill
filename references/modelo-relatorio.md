# Modelo do relatório final

## 🔐 Auditoria preventiva — [projeto]
**Alvo:** [URL/caminho]  
**Data e horário UTC:** [...]  
**Versão/commit auditado:** [...]  
**Escopo e método:** [arquivos lidos, consultas, análise estática, recursos indisponíveis]  
**Veredito:** [🟢 / 🟡 / 🟠 / 🔴] — [frase direta]

### 1. O que o projeto faz
[Objetivo, linguagem, modos de uso e funcionalidades opcionais.]

### 2. Reputação e manutenção
[Estrelas, forks, criação, último commit, autores, cadência, issues/PRs, releases, suspeitas e limites.]

### 3. Principais achados, do mais grave ao menos grave
Para cada um:
- **[R-01] Título — Gravidade / Confiança**
- **Evidência:** `caminho:linhas` + link permanente; trecho curto
- **O que faz:** explicação simples
- **Quando ocorre:** instalação, execução manual, pós-instalação, hook, opção etc.
- **Por que importa:** consequência plausível, distinguindo risco de intenção
- **Mitigação:** ação prática

### 4. Instalação, privilégios e persistência
[Comandos do README explicados; scripts automáticos, hooks, serviços, scheduler, antivirus.]

### 5. Rede e dados
| Domínio/endereço | Arquivo/linha | O que envia/baixa | Condição | Avaliação |
|---|---|---|---|---|
[Inclua destinos configuráveis separadamente e credenciais potencialmente usadas.]

### 6. Dependências, Actions e releases
[Pacotes/versões, scripts, vulnerabilidades verificadas, downloads binários, CI, relação source/release.]

### 7. VirusTotal e hashes
[Resultados verificáveis; caso contrário: NÃO FOI POSSÍVEL VERIFICAR.]

### 8. Cobertura e limitações
**Verificado:** [itens]  
**NÃO FOI POSSÍVEL VERIFICAR:** [itens]  
**Não realizado:** [análise dinâmica, execução, revisão exaustiva etc.]

### 9. Conclusão e instalação mais segura
[Recomendação inequívoca; passos de isolamento proporcionais ao risco, sem executar nada durante a auditoria.]

### 10. RESUMO FINAL
**PROJETO:** [...]  
**REPOSITÓRIO:** [...]  
**REPUTAÇÃO:** [Boa / Média / Ruim / Incerta]  
**SINAIS SUSPEITOS:** [...]  
**ARQUIVOS MAIS SENSÍVEIS:** [...]  
**CONEXÕES EXTERNAS:** [...]  
**DEPENDÊNCIAS SUSPEITAS:** [...]  
**DETECÇÕES DE ANTIVÍRUS:** [resultado / NÃO FOI POSSÍVEL VERIFICAR]  
**RISCO ESTIMADO:** [Baixo / Moderado / Alto / Crítico]  
**RECOMENDAÇÃO:** [Instalar / Somente em ambiente isolado / Não instalar + justificativa]

> **Distinção obrigatória:** “Não encontrei comportamento malicioso” não significa “é comprovadamente seguro”.
