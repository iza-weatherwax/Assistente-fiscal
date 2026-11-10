# Assistente Fiscal

Um único arquivo, `assistente-fiscal.html`. Basta abri-lo no navegador (Chrome ou Edge), sem instalar nada e sem internet.

## Como usar

1. Abra `assistente-fiscal.html`. Cada auditoria é um **processo**; use “＋ Novo processo” para começar outro.
2. No topo, responda as três condições: **Empresa baixada?**, **Matriz em outra UF?** e **Anexo V (fator R)?**. Enquanto a situação cadastral não for verificada, a faixa vermelha fica piscando.
3. Siga as etapas. A etapa amarela é a próxima pendente; você pode marcar fora de ordem, e a página avisa se ficou algo para trás.
4. Preencha os **dados do processo** (CNPJ, OS, TIAF…) uma só vez: eles aparecem nas etapas em que são usados, com botão de copiar. Os textos em azul dentro dos passos também copiam ao clicar.
5. Use as observações de cada etapa; marque “Lembrete” para a nota ficar em destaque até ser resolvida.

## Ajudas dentro das etapas

- **Sistema e usuário:** abaixo do título de cada etapa aparece em que sistema ela é feita e com qual usuário (ex.: “GFT · usuário do Divino” na etapa 3 e “GFT · seu usuário de auditor” na etapa 5).
- **Dicas em amarelo (💡):** logo abaixo dos passos, com os avisos do tutorial (clicar na lupa no GSN, conferir o ano, salvar como OS1…).
- **Período fiscalizado:** digite uma vez “de” e “até” (mm/aaaa); os botões de copiar já trazem cada formato que os sistemas pedem: 01/01/2021 e 31/12/2021 (OS, NFe-cidades), 01/2021 e 12/2021 (Simples Nacional) e 2021 (GSN).
- **Botão “Hoje”** nos campos de data e campo **CNPJ básico** (8 primeiros dígitos, antes do 0001), preenchido sozinho a partir do CNPJ, para o GSN e o Lavrar AINF.
- **Notificação prévia (etapa 2):** lembrete para salvar a notificação do GSN e campos para o nº da notificação (monitoramento fiscal) e a data de ciência.
- **CNAE** (etapa 0): aparece de novo na apuração (etapa 9), para achar o anexo correto.
- **CNPJ e CPF conferidos:** se o dígito verificador não bater, o campo fica vermelho.
- **MEI:** se a razão social terminar com um CPF, a página oferece incluí-lo como sócio.
- **Passos “se for o caso”:** têm o botão “não se aplica”, que conta como resolvido sem marcar como feito.

## Sócios, e-mails prontos e marcação em lote

- **Sócios:** na etapa 4 (e na lateral) dá para incluir quantos sócios houver, cada um com nome e CPF e botões de copiar. Na etapa 7, o passo “Preencher apenas CPF” mostra um botão de copiar por sócio.
- **E-mails prontos:** a etapa 6 traz o texto do e-mail do TIAF pronto; é só clicar em “Copiar e-mail”. O texto é editável e vale para todos os processos. As etapas 9A (intimação) e 14 (AINF) têm modelos vazios para você colar os seus. Dentro do texto, `$nome`, `$cnpj`, `$os`… são trocados pelos dados do processo na hora de copiar.
- **Texto do TCAF (etapa 12):** o texto do Termo de Conclusão já vem preenchido com a data e o nº da notificação, o nº da ação fiscal e o que a apuração encontrou (DBC, SIR ou os dois, escolhido na etapa 9). A prévia mostra em vermelho o que ainda falta preencher; “Copiar texto” copia pronto para colar no GFT.
- **Marcar em lote:** cada etapa tem “Marcar todos os passos desta etapa” e “Desmarcar todos”; no topo, “Marcar tudo”. Em lote, ficam de fora as conferências (em amarelo), os passos que liberam esperas, as etapas travadas e a etapa 13 enquanto a situação da empresa não for verificada.

## Guardar e consultar processos antigos

- Tudo é salvo automaticamente no navegador.
- **Arquivo de dados (JSON único):** no Chrome/Edge, “Arquivo de dados” (na lateral) liga a página a **um só arquivo** com todos os processos, os dados fixos e os modelos de e-mail. Ele é regravado a cada alteração, e o navegador lembra o arquivo (às vezes pede para reconectar). Ao ligar um arquivo que já existe, o conteúdo é juntado ao que está na página: de cada processo vale a versão mais recente.
- **Baixar JSON** baixa só o processo aberto; **Baixar tudo agora** baixa tudo; **Abrir JSON** reabre qualquer um. Os nomes são sempre os mesmos, para você substituir em vez de acumular arquivos.
- Cada processo guarda marcações com data e hora, dados, observações (também com data e hora) e o roteiro usado.
- Os JSON têm CNPJ e dados sigilosos: o `.gitignore` já os mantém fora do repositório.

## Cores

| Cor | Significado |
|---|---|
| Vermelho | Alerta ou pendência obrigatória |
| Roxo | Empresa baixada |
| Laranja | Prazo/espera (outra UF, intimação do Anexo V, prazo da fiscalização perto) |
| Amarelo | Próxima etapa, conferências e lembretes |
| Verde | Concluído |
| Azul | Dados e botões de copiar |

## Prazos e travas

- **Prazo da fiscalização:** 90 dias a partir da data ciente da OS (ou a data final que você anotar na etapa 7). Aparece no topo; a faixa acende quando faltam 15 dias ou menos. Para de contar quando a etapa 14 é concluída.
- **Decadência:** anote na etapa 1 a decadência mais próxima que o Portal Apura mostrar. A faixa vermelha acende quando faltam 30 dias ou menos; para de contar quando a ciência do lançamento (etapa 15) é registrada.
- Os dois prazos também aparecem no aviso de outros processos quando estão perto.

- **Matriz em outra UF = Sim:** aparece a etapa 7A (10 dias corridos a partir do registro da ação fiscal no Simples Nacional). As etapas seguintes ficam travadas até o fim do prazo.
- **Anexo V = Sim:** entram as etapas 9A e 9B (termo de intimação de 10 dias corridos contados da leitura do e-mail; só depois a apuração termina). A trava se desfaz ao marcar “Folha de pagamento recebida” ou quando o prazo vence.
- Em ambos os casos há o botão “Liberar mesmo assim”, que pede confirmação.

## Editar o roteiro

O botão **Editar roteiro** abre o roteiro em formato de texto; a ajuda no próprio editor explica a sintaxe. Dá para aplicar só ao processo aberto ou salvar como modelo dos próximos. Cada processo guarda a cópia do roteiro que usou.
