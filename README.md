# Assistente Fiscal

Um único arquivo, `assistente-fiscal.html`. Basta abri-lo no navegador (Chrome ou Edge), sem instalar nada e sem internet.

## Como usar

1. Abra `assistente-fiscal.html`. Cada auditoria é um **processo**; use “＋ Novo processo” para começar outro.
2. No topo, responda as três condições: **Empresa baixada?**, **Matriz em outra UF?** e **Anexo V (fator R)?**. Enquanto a situação cadastral não for verificada, a faixa vermelha fica piscando.
3. Siga as etapas. A etapa amarela é a próxima pendente; você pode marcar fora de ordem, e a página avisa se ficou algo para trás.
4. Preencha os **dados do processo** (CNPJ, OS, TIAF…) uma só vez: eles aparecem nas etapas em que são usados, com botão de copiar. Os textos em azul dentro dos passos também copiam ao clicar.
5. Use as observações de cada etapa; marque “Lembrete” para a nota ficar em destaque até ser resolvida.

## Sócios, e-mails prontos e marcação em lote

- **Sócios:** na etapa 4 (e na lateral) dá para incluir quantos sócios houver, cada um com nome e CPF e botões de copiar. Na etapa 7, o passo “Preencher apenas CPF” mostra um botão de copiar por sócio.
- **E-mails prontos:** a etapa 6 traz o texto do e-mail do TIAF pronto; é só clicar em “Copiar e-mail”. O texto é editável e vale para todos os processos. As etapas 9A (intimação) e 14 (AINF) têm modelos vazios para você colar os seus. Dentro do texto, `$nome`, `$cnpj`, `$os`… são trocados pelos dados do processo na hora de copiar.
- **Marcar em lote:** cada etapa tem “Marcar todos os passos desta etapa” e “Desmarcar todos”; no topo, “Marcar tudo”. Em lote, ficam de fora as conferências (em amarelo), os passos que liberam esperas, as etapas travadas e a etapa 13 enquanto a situação da empresa não for verificada.

## Guardar e consultar processos antigos

- Tudo é salvo automaticamente no navegador.
- **Arquivo de dados (JSON único):** no Chrome/Edge, “Arquivo de dados” (na lateral) liga a página a **um só arquivo** com todos os processos, os dados fixos e os modelos de e-mail. Ele é regravado a cada alteração, e o navegador lembra o arquivo (às vezes pede para reconectar). Ao ligar um arquivo que já existe, o conteúdo é juntado ao que está na página: de cada processo vale a versão mais recente.
- **Baixar JSON** baixa só o processo aberto; **Baixar tudo agora** baixa tudo; **Abrir JSON** reabre qualquer um. Os nomes são sempre os mesmos, para você substituir em vez de acumular arquivos.
- Cada processo guarda marcações com data e hora, dados, observações, histórico e o roteiro usado.
- Os JSON têm CNPJ e dados sigilosos: o `.gitignore` já os mantém fora do repositório.

## Cores

| Cor | Significado |
|---|---|
| Vermelho | Alerta ou pendência obrigatória |
| Roxo | Empresa baixada |
| Laranja | Prazo/espera (outra UF, intimação do Anexo V) |
| Amarelo | Próxima etapa, conferências e lembretes |
| Verde | Concluído |
| Azul | Dados e botões de copiar |

## Prazos e travas

- **Matriz em outra UF = Sim:** aparece a etapa 7A (10 dias corridos a partir do registro da ação fiscal no Simples Nacional). As etapas seguintes ficam travadas até o fim do prazo.
- **Anexo V = Sim:** entram as etapas 9A e 9B (termo de intimação de 10 dias corridos contados da leitura do e-mail; só depois a apuração termina). A trava se desfaz ao marcar “Folha de pagamento recebida” ou quando o prazo vence.
- Em ambos os casos há o botão “Liberar mesmo assim”, que pede confirmação.

## Editar o roteiro

O botão **Editar roteiro** abre o roteiro em formato de texto; a ajuda no próprio editor explica a sintaxe. Dá para aplicar só ao processo aberto ou salvar como modelo dos próximos. Cada processo guarda a cópia do roteiro que usou.
