# Os três tipos de plataformas de fluxo de trabalho do SharePoint
A plataforma de fluxo de trabalho do SharePoint 2010 foi encaminhada para Office 365 e o SharePoint Server 2013 e, portanto, todos os fluxos de trabalho criados nessa plataforma continuam funcionando. Essa plataforma é baseada no Windows Workflow Foundation 3.5 (WF3.5).

A plataforma de fluxo de trabalho do SharePoint 2013 é baseada no WF (Windows Workflow Foundation 4) e é substancialmente redesenhada. Talvez o recurso mais proeminente dessa nova plataforma de fluxo de trabalho seja o uso do Microsoft Azure como o host de execução do fluxo de trabalho. O mecanismo de execução do fluxo de trabalho agora vive fora do Office 365 e do SharePoint Server 2013, no Microsoft Azure.

No SharePoint Online, o Microsoft Flow já está disponível. Este é o mais novo mecanismo de fluxo de trabalho, acesse em: https://flow.microsoft.com . Para saber mais sobre como usar o MS Flow, visite: https://docs.microsoft.com/en-us/flow . Para solucionar problemas do MS Flow, visite, https://docs.microsoft.com/en-us/flow/fix-flow-failures & https://us.flow.microsoft.com/en-us/support/

# Fluxos de trabalho internos
Um site do SharePoint inclui vários fluxos de trabalho internos que abordam cenários de negócios comuns:

- Aprovação Este fluxo de trabalho encaminha um documento ou item a um grupo de pessoas para aprovação. Por padrão, o fluxo de trabalho Aprovação está associado ao tipo de conteúdo Documento e, portanto, fica automaticamente disponível nas bibliotecas de documentos.

# Coletar Comentários     
- Este fluxo de trabalho encaminha um documento ou item a um grupo de pessoas para obter comentários. Os revisores podem fornecer comentários, que serão compilados e enviados para a pessoa que iniciou o fluxo de trabalho. Por padrão, o fluxo de trabalho Coletar Comentários está associado ao tipo de conteúdo Documento e, portanto, fica automaticamente disponível nas bibliotecas de documentos.

# Coletar Assinaturas 
- Este fluxo de trabalho encaminha um documento do Microsoft Office a um grupo de pessoas para coletar suas assinaturas digitais. Esse fluxo de trabalho deve ser iniciado em um programa do Office 2013. Os participantes devem concluir suas tarefas de assinatura adicionando sua assinatura digital ao documento no programa relevante do Office. Por padrão, o fluxo de trabalho Coletar Assinaturas está associado ao tipo de conteúdo Documento e, portanto, fica automaticamente disponível nas bibliotecas de documentos. No entanto, o fluxo de trabalho Coletar Assinaturas aparecerá para um documento somente na biblioteca de documentos, caso esse documento contenha uma ou mais linhas de assinatura do Microsoft Office.

# Aprovação para Publicação     

- Este fluxo de trabalho é semelhante ao fluxo de trabalho Aprovação no sentido de que automatiza o encaminhamento de conteúdo aos especialistas no assunto e a outros participantes, para revisão e aprovação. O que torna o fluxo de trabalho de aprovação para publicação único é que ele foi projetado especificamente para publicar sites em que a publicação de páginas da Web novas e atualizadas é rigidamente controlada.

# Três estados     

- Este fluxo de trabalho pode ser usado para gerenciar processos empresariais que requerem que as organizações controlem um alto volume de problemas, vendas potenciais ou tarefas do projeto.

Cada um dos fluxos de trabalho acima pode ser personalizado para sua organização de várias maneiras. Por exemplo, ao adicionar um fluxo de trabalho a uma lista, biblioteca ou tipo de conteúdo para disponibilizá-lo em documentos ou itens, é possível personalizar as listas de tarefas e as listas de histórico onde as informações sobre o fluxo de trabalho estão armazenadas.

Quando um usuário do site iniciar um fluxo de trabalho em um documento ou item, ele poderá ter a opção de personalizá-lo ainda mais, especificando a lista de participantes, uma data de conclusão e instruções sobre a tarefa.
