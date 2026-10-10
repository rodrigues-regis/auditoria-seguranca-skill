# Checklist técnico de auditoria estática

Este checklist orienta a busca; ocorrência textual isolada NÃO constitui malware. Sempre verifique contexto, alcance e condição de execução.

## 1. Reputação e autoria
- Estrelas, forks, idade, commits, releases, contributors, issues/PRs, reclamações, eventos de propriedade, branches e tags, SECURITY.md e alertas públicos.
- Mantenedores e mudanças recentes; distinguir conta antiga de repositório novo.

## 2. Arquivos e superfícies de instalação
- Extensões: `.exe`, `.msi`, `.dll`, `.bat`, `.cmd`, `.ps1`, `.vbs`, `.js`, `.scr`, `.jar`, `.sh`, `.app`, `.dmg`, `.pkg`, `.zip`, `.rar`, `.7z`, `.so`, `.dylib`, `.whl`, `.node`.
- Arquivos: `install.ps1`, `install.bat`, `setup.py`, `setup.sh`, `install.sh`, `Makefile`, `Dockerfile*`, `compose.y*ml`, `package.json`, `pyproject.toml`, `requirements*.txt`, `postinstall`, `preinstall`, scripts npm, hooks e entrypoints.
- Comandos no README: `curl ... | bash`, `wget ... | sh`, `irm ... | iex`, `powershell -Command`, `npm install -g`, `pip install`, `pip install git+`, `npx`. Explique efeitos e transitive dependencies.

## 3. Execução de código, elevação e ofuscação
- `Invoke-WebRequest`, `Invoke-RestMethod`, `Invoke-Expression`, `IEX`, `DownloadString`, `Start-Process`, `powershell -enc`, `cmd.exe`, `certutil`, `bitsadmin`, `rundll32`, `regsvr32`, `mshta`, `wscript`, `cscript`.
- `eval`, `exec`, `Function`, `subprocess`, `os.system`, `shell=True`, `child_process`, `spawn`, comandos indiretos, `base64`, XOR, strings montadas, payloads descriptografados, blobs longos/minificados.
- `runas`, UAC, `sudo`, admin/root, `SeDebugPrivilege` e permissões em Docker/Kubernetes.

## 4. Rede, downloads e segredos
- HTTP(S), WebSocket, sockets, APIs, endpoints hardcoded/configuráveis, IPs, DNS, redirects, proxy, Discord webhooks, Telegram Bot API, S3 e paste sites.
- `Authorization`, bearer/API keys, env vars, `.env`, tokens GitHub/Hugging Face, logs que podem vazar segredos.
- Acesso a senhas/cookies/sessões/histórico dos navegadores Chrome/Edge/Firefox/Brave, Discord, Telegram, Steam e wallets.
- Strings-alvo: `Login Data`, `Cookies`, `Local State`, `Web Data`, `key4.db`, `logins.json`, `wallet.dat`.
- Separe downloads legítimos de modelos e dependências de downloads com execução imediata ou sem integridade.

## 5. Persistência, defesa e comportamento hostil
- Registry `Run`/`RunOnce`, Startup Folder, Scheduled Tasks, Services, WMI, DLL hijacking, launch agents, cron e systemd.
- Defender, exclusões, firewall, políticas e instruções para desativar antivírus.
- Keylogging, captura de tela, microfone, webcam, clipboard, injeção, process hollowing, DLL injection, RAT, reverse shell, dropper, miner, clipper, C2, anti-debug, anti-VM, anti-sandbox, autodeleção, limpeza de logs.

## 6. Dependências e automação
- Manifestos/locks: `requirements.txt`, `pyproject.toml`, `package.json`, `package-lock.json`, `yarn.lock`, `pnpm-lock.yaml`, `Cargo.lock`, `go.sum` e equivalentes.
- Typosquatting, pacotes novos/desconhecidos, git URLs, tags móveis, scripts de instalação, lockfile ausente, pins desatualizados/CVEs confirmados.
- `.github/workflows/`: secrets, permissões, `pull_request_target`, artefatos, tags/digests de Actions, downloads, publish jobs e riscos de PR externo.

## 7. Distribuição e reputação de binários
- Releases versus tag e árvore da fonte; GHCR/Docker Hub, PyPI/npm, instaladores e hashes/assinaturas oficiais.
- VirusTotal só com hash associado inequivocamente ao arquivo; data, engines, detecções e falsos positivos contextualizados. Se não verificável, registre a limitação.

## 8. Registro mínimo por achado
- ID/severidade; arquivo + link para commit e linhas; trecho curto; o que faz; como é ativado; destino/artefato quando aplicável; por que é preocupante; mitigação; grau de confiança.
