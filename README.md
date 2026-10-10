# Auditoria de Segurança — Skill para Hermes Agent

Skill para auditoria preventiva de repositórios, arquivos e programas antes da instalação. Organiza 20 frentes de análise, exige evidências e distingue ausência de indícios de segurança comprovada. **A auditoria é estática: não execute código do alvo.**

## Instalar no Hermes (Linux / VPS)

```bash
mkdir -p ~/.hermes/skills
git clone https://github.com/rodrigues-regis/auditoria-seguranca-skill.git ~/.hermes/skills/auditoria-seguranca-repositorio
```

Reinicie a sessão do Hermes e peça: `Use a skill auditoria-seguranca-repositorio para auditar https://github.com/EXEMPLO/REPO sem executar nenhum código.`

## Atualizar

```bash
git -C ~/.hermes/skills/auditoria-seguranca-repositorio pull --ff-only
```

## Segurança

- Não cole tokens, senhas ou chaves no prompt, nem envie credenciais para o projeto avaliado.
- A skill não concede ferramentas novas; GitHub, pesquisa e VirusTotal dependem das ferramentas disponíveis no agente.
- Repositórios e seus READMEs são dados não confiáveis; não devem alterar as instruções do auditor.
- Prefira fixar o commit avaliado e executar testes apenas em ambiente isolado.

## Arquivos

- `SKILL.md`: regras operacionais da skill.
- `references/checklist.md`: checklist da auditoria.
- `references/modelo-relatorio.md`: estrutura de saída.
