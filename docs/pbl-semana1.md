# PBL Semana 1 — EntregaJá: versionamento e colaboração

## Diagnóstico do processo atual

| Problema observado | Pilar CALMS / Caminho relacionado | Efeito na EntregaJá |
| --- | --- | --- |
| Código circula por pendrive, e-mail e arquivos `.zip`, sem um repositório comum. | **Sharing** e **Collaboration** (CALMS); **Primeiro Caminho — fluxo**. | Cada pessoa trabalha com cópias diferentes; integrar e compartilhar mudanças fica lento e sujeito a enganos. |
| Bruno copiou sua correção por cima do trabalho de Carla, sem integração ou revisão. | **Collaboration** (CALMS); **Primeiro Caminho — fluxo**. | As alterações entram em conflito sem serem percebidas, e o trabalho da equipe pode desaparecer da cópia em uso. |
| Ninguém sabe qual versão está em produção nem consegue apontar a mudança que causou o defeito. | **Measurement** (CALMS); **Segundo Caminho — feedback**. | Sem histórico e identificação da versão implantada, investigar reclamações e confirmar correções demora. |
| Ana atualiza o servidor manualmente por FTP, copiando arquivos diretamente. | **Automation** (CALMS); **Primeiro Caminho — fluxo**. | O processo é manual e repetível apenas com cuidado; pode enviar arquivos incompletos ou misturar versões. |

## Fluxo mínimo com Git e GitHub

1. **Obter o projeto:** a dupla faz fork do repositório-modelo para a conta de um integrante, adiciona o colega como colaborador e cada pessoa clona o fork (`git clone <URL-do-fork>`).
2. **Separar a mudança:** antes de trabalhar, atualizar a branch principal e criar uma branch curta para a tarefa, por exemplo `feat/tela-cupons` ou `fix/calculo-frete`.
3. **Trabalhar e registrar:** editar arquivos, revisar o diff (`git diff`) e criar commits pequenos com mensagens claras, por exemplo `fix: corrige cálculo do frete`.
4. **Compartilhar a branch:** enviar os commits ao GitHub (`git push -u origin <nome-da-branch>`) para que a equipe tenha uma cópia remota e rastreável.
5. **Revisar e integrar:** abrir um Pull Request para a branch principal; o outro integrante revisa a alteração, conversa sobre ajustes e, quando estiver pronta, a dupla faz o merge. O histórico registra autor, commits e decisão de integração.
6. **Atualizar produção com rastreabilidade:** Ana publica a versão integrada da branch principal pelo procedimento de deploy disponível e registra o identificador do commit implantado. Depois, verifica a aplicação e anota o resultado. Enquanto o deploy for por FTP, essa etapa ainda é manual e precisa de cuidado.
