# Assistente Fiscal

Um único arquivo, `assistente-fiscal.html`. Basta abri-lo no navegador (Chrome ou Edge), sem instalar nada e sem internet.

## Como usar

1. Abra `assistente-fiscal.html`. Cada auditoria é um **processo**; use “＋ Novo processo” para começar outro.
2. No topo, responda as três condições: **Empresa baixada?**, **Matriz em outra UF?** e **Anexo V (fator R)?**. Enquanto a situação cadastral não for verificada, a faixa vermelha fica piscando.
3. Siga as etapas. A etapa amarela é a próxima pendente; você pode marcar fora de ordem, e a página avisa se ficou algo para trás.
4. Preencha os **dados do processo** (CNPJ, OS, TIAF…) uma só vez: eles aparecem nas etapas em que são usados, com botão de copiar. Os textos em azul dentro dos passos também copiam ao clicar.
5. Use as observações de cada etapa; marque “Lembrete” para a nota ficar em destaque até ser resolvida.

## Guardar e consultar processos antigos

- Tudo é salvo automaticamente no navegador.
- **Salvar JSON** baixa o processo completo: marcações com data e hora, dados, observações, histórico e o roteiro usado. **Abrir JSON** reabre qualquer processo antigo.
- No Chrome/Edge, “Salvar sempre em um arquivo…” grava o JSON a cada alteração, no mesmo arquivo.
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
