# Desafio LAbs Github </p>
Link: https://github.com/MicrosoftLearning/MS-100T00-Microsoft-365-Identity-and-Services/tree/master/Instructions/Labs

# Laboratório 1  

# Exercício 1 - Inicializar seu locatário do Microsoft 365]

Adatum Corporation é uma subsidiária da Contoso Electronics. A Adatum executa seus aplicativos legados (como o Microsoft Exchange Server 2019) em uma implantação local. No entanto, recentemente se inscreveu no Microsoft 365, criando assim uma implantação híbrida na qual deve sincronizar suas implantações locais e na nuvem.

Como administrador corporativo da Adatum, você foi encarregado de implantar o Microsoft 365 na implantação híbrida da Adatum usando um ambiente de laboratório virtualizado. Neste exercício, você configurará o locatário de avaliação do Microsoft 365 da Adatum e seu instrutor o orientará sobre como obter suas credenciais do Microsoft 365 em seu ambiente hospedado em laboratório. Você usará essas credenciais nos laboratórios restantes deste curso.

Em seu ambiente de laboratório, seu provedor de hospedagem de laboratório já obteve um locatário de avaliação do Microsoft 365 para você. Seu provedor de laboratório também criou duas contas de administrador que você usará em seu ambiente de laboratório VM:

Uma conta de administrador local para o ambiente local da Adatum (Adatum\Administrador).
Uma conta de administrador de locatário padrão no Microsoft 365 (o nome de exibição dessa conta de usuário é MOD Administrator).
Você fará login na VM do controlador de domínio (LON-DC1) usando a conta local Adatum\Administrator. Ao acessar o Microsoft 365 pela primeira vez, você fará login inicialmente usando a conta de administrador do locatário do Microsoft 365 (Administrador do MOD). Em seguida, você atualizará o perfil organizacional do Microsoft 365 da Adatum e preparará seu locatário para o Microsoft Azure Active Directory e para um laboratório futuro usando o Microsoft Teams.

Tarefa 1 - Obtenha suas credenciais do Microsoft 365
Depois de iniciar o laboratório, você poderá acessar o locatário de avaliação gratuita do Microsoft 365 fornecido pelo seu provedor de hospedagem de laboratório no ambiente Microsoft Virtual Lab. Nesse locatário, seu provedor de hospedagem de laboratório criou uma conta de usuário do Microsoft 365 para um administrador de locatário padrão chamado MOD Administrator. Seu provedor de hospedagem de laboratório atribuiu a esta conta de usuário um nome de usuário e senha exclusivos, e a conta foi atribuída à função de administrador global do Microsoft 365. Você deve recuperar esse nome de usuário e senha para poder entrar no Microsoft 365 no ambiente Microsoft Virtual Lab. Você também receberá um endereço IP de rede exclusivo e um nome UPN para seu blob do Microsoft 365. Você também usará esse nome UPN em várias tarefas nos laboratórios deste curso.

Como este curso pode ser oferecido por parceiros de aprendizado usando qualquer um dos vários provedores autorizados de hospedagem de laboratório, as etapas reais envolvidas para recuperar o nome UPN, o endereço IP da rede e a ID do locatário associados ao seu locatário podem variar de acordo com o provedor de hospedagem do laboratório. Portanto, seu instrutor fornecerá as instruções necessárias sobre como recuperar essas informações para seu curso.

Link: https://github.com/MicrosoftLearning/MS-100T00-Microsoft-365-Identity-and-Services/blob/master/Instructions/Labs/LAB_AK_02_Lab1_Ex1_Initialize_M365_Tenant.md


# Exercício 2 - Gerenciar usuários e grupos
No próximo exercício de laboratório, você continuará em sua função como Holly Dickson, administradora corporativa da Adatum Corporation. Neste exercício, você executará várias funções de gerenciamento de usuários e grupos no Microsoft 365. Você começará criando uma conta de usuário do Microsoft 365 para Holly, a quem será atribuída a função de administrador global. Você criará dois grupos do Microsoft 365 e atribuirá usuários existentes do Microsoft 365 como membros desses grupos. Em seguida, você excluirá um dos grupos e usará o Windows PowerShell para recuperar o grupo excluído.

Observação: o ambiente VM fornecido pelo seu provedor de hospedagem de laboratório vem com 11 contas de usuário existentes do Microsoft 365, bem como um grande número de contas de usuário locais existentes. Várias das contas de usuário existentes do Microsoft 365 serão usadas nos laboratórios deste curso. Mesmo que a conta do Administrador do MOD tenha sido criada para você pelo seu provedor de hospedagem de laboratório, você ainda criará a conta de usuário de Holly Dickson, pois ter mais de um administrador global é uma prática recomendada. Ele também fornecerá a você a experiência de criar uma conta de usuário do Microsoft 365, caso você não esteja familiarizado com o processo.

LInk: https://github.com/MicrosoftLearning/MS-100T00-Microsoft-365-Identity-and-Services/blob/master/Instructions/Labs/LAB_AK_02_Lab1_Ex2_Manage_Users_and_Groups.md


# Exercício 3 - Adicionar um domínio personalizado
Nem toda empresa possui apenas um domínio; na verdade, muitas empresas têm mais de um domínio. A Adatum acaba de adquirir um novo domínio (xxxUPNxxx.xxxCustomDomainxxx.xxx; cujo nome exato é fornecido pelo seu provedor de hospedagem de laboratório) que reside no Microsoft Azure, mas não no ambiente local da Adatum. Para oferecer suporte ao novo domínio personalizado da Adatum, seu provedor de hospedagem de laboratório assumiu a função de registrador de domínio terceirizado da Adatum.

Neste exercício, você ganhará experiência adicionando este domínio à implantação do Microsoft 365 da Adatum. Quando você adiciona um domínio ao Microsoft 365, ele é chamado de domínio aceito ou personalizado. Os domínios personalizados permitem que as empresas tenham sua própria marca em emails e contas para que os clientes possam verificar quem está enviando o email (por exemplo, @contoso.com). Quando uma empresa adiciona um novo domínio ao Microsoft 365, ela também deve manter os registros DNS necessários para dar suporte aos serviços exigidos pela empresa para o novo domínio.

A maioria das empresas não gerencia pessoalmente os registros DNS de seus domínios; em vez disso, eles têm um recurso terceirizado que gerencia esses registros para eles. Para ajudar nesse esforço, o Microsoft 365 fornece a determinados registradores de domínio de terceiros uma ferramenta de automação que adiciona e substitui automaticamente os registros DNS de uma empresa. A ferramenta de automação também federa as credenciais de entrada para os registradores de terceiros e o Microsoft 365. Usar uma ferramenta para manter automaticamente os registros DNS é uma melhoria muito bem-vinda desde os dias em que as empresas tinham que manter esses registros manualmente, o que muitas vezes introduzia erro humano em um processo bastante complicado. Como essas ferramentas eliminam a necessidade de adicionar manualmente os registros DNS, elas eliminam o erro humano do processo.

Dito isso, para este laboratório, você será solicitado a criar manualmente os registros DNS necessários exigidos por este novo domínio personalizado. Nos outros cursos de treinamento do Microsoft 365 que usam um domínio personalizado (como MS-101T00 e MS-030T00), o domínio personalizado e seus registros DNS serão adicionados à implantação do Microsoft 365 da Adatum pelo provedor de hospedagem do laboratório, que assumirá o papel do registrador de domínio de terceiros para Adatum. No entanto, este curso de treinamento MS-100T00 o incumbirá de adicionar o domínio e criar os registros DNS necessários para que você ganhe experiência e compreensão sobre o que são os registros DNS e por que eles são necessários para um novo domínio.

Link: https://github.com/MicrosoftLearning/MS-100T00-Microsoft-365-Identity-and-Services/blob/master/Instructions/Labs/LAB_AK_02_Lab1_Ex3_Add_a_Domain.md


# Laboratorio 2

# Exercício 1 - Gerenciar delegação de administração
Neste exercício, você continuará em sua função como Holly Dickson, administradora corporativa da Adatum. Como parte do projeto piloto do Microsoft 365 da Adatum, você gerenciará a delegação de administração atribuindo funções de administrador do Microsoft 365 a várias das contas de usuário do Microsoft 365 que foram criadas pelo seu provedor de hospedagem de laboratório. Você atribuirá essas funções usando o centro de administração do Microsoft 365 e o Windows PowerShell; isso lhe dará a experiência adicional de usar o PowerShell para executar essas funções administrativas. Depois de atribuir funções de administrador do Microsoft 365 a várias contas de usuário existentes, você testará essas atribuições verificando se os usuários têm permissões para agir de acordo com suas funções.

Link:https://github.com/MicrosoftLearning/MS-100T00-Microsoft-365-Identity-and-Services/blob/master/Instructions/Labs/LAB_AK_03_Lab2_Ex1_Manage_Admin_Delegation.md

# Exercício 2 - Monitorar e solucionar problemas do Microsoft 365
Neste exercício, você conhecerá algumas ferramentas de solução de problemas no Microsoft 365 que permitem solucionar problemas de fluxo de emails. Em seguida, você analisará a integridade do serviço Microsoft 365 da Adatum revisando várias das principais consultas e relatórios de integridade do serviço disponíveis no Microsoft 365. Você concluirá este exercício revisando como enviar uma solicitação de serviço à equipe de suporte da Microsoft caso precise de ajuda com um problema.

Link: https://github.com/MicrosoftLearning/MS-100T00-Microsoft-365-Identity-and-Services/blob/master/Instructions/Labs/LAB_AK_03_Lab2_Ex2_Monitor_Office_365.md

# Exercício 3 - Gerenciar uma instalação de aplicativos do Microsoft 365 para empresas
Você assumiu a personalidade de Holly Dickson, administradora corporativa da Adatum, e implantou o Microsoft 365 em um ambiente de laboratório virtualizado. Neste exercício, você executará as tarefas necessárias para gerenciar uma instalação de aplicativos do Microsoft 365 para empresas orientada pelo usuário. A execução de uma instalação de aplicativos do Microsoft 365 para empresas orientada pelo usuário é um processo de duas etapas: 1) configurar a conta de usuário para que o usuário seja elegível para baixar e instalar a ferramenta de implantação do Office 365 e 2) executar a instalação.

Nas duas primeiras tarefas deste exercício, você verificará as seguintes condições que afetam se um usuário pode ser impedido de baixar o Microsoft 365 Apps for Enterprise Suite:

O usuário não possui uma licença apropriada do Office 365 (que você verificará na Tarefa 1).

Um administrador desativa a configuração global de download do Office que controla o download de aplicativos móveis e de desktop para todos os usuários (que você verificará na Tarefa 2).

Na tarefa final deste exercício, você instalará o pacote Microsoft 365 Apps for Enterprise para um dos usuários da Adatum.

Link: https://github.com/MicrosoftLearning/MS-100T00-Microsoft-365-Identity-and-Services/blob/master/Instructions/Labs/LAB_AK_03_Lab2_Ex3_M365_Apps.md


# Laboratório 3  

# Exercício 1 - Crie um relatório e um painel do Power BI
Holly Dickson está chegando ao fim de sua excursão ao ambiente Microsoft Power Platform. Ela criou dois Power Apps e um Power Automate Flow, todos baseados no sistema de tíquetes do Service Desk que ela criou anteriormente no SharePoint.

Ela agora também está interessada em criar e compartilhar um relatório e um painel do Power BI com base no sistema de tickets do SharePoint. O consultor de TI da Adatum sugeriu que ela usasse o Power BI Desktop, um aplicativo gratuito que ela pode instalar localmente e que permitirá que ela se conecte, transforme e visualize os dados do sistema de tíquetes. Ela pode usar o Power BI Desktop para criar relatórios e, em seguida, usar o serviço Power BI para compartilhar seus relatórios com outras pessoas.

Em sua função como Holly Dickson, você usará este exercício para criar algumas visualizações básicas para um relatório do Power BI; as visualizações serão baseadas na lista de Solicitações do Service Desk no site da equipe do SharePoint intitulado Serviços de TI .

Link: https://github.com/MicrosoftLearning/MS-100T00-Microsoft-365-Identity-and-Services/blob/master/Instructions/Labs/LAB_AK_04_Lab3_Ex10_Power_BI_report.md

# Exercício 2 - Revise os principais recursos do Exchange Online
Holly Dickson é a administradora corporativa de Adatum. Ela implantou recentemente o Microsoft 365 em um ambiente de laboratório virtualizado. Agora que ela tem uma conta de locatário configurada e foi atribuída à função de administrador global, ela foi solicitada a revisar as principais funções administrativas no Exchange Online, SharePoint Online e Teams. Essa tarefa permitirá que ela se familiarize com sua funcionalidade e possa oferecer orientação à sua equipe de TI sobre como esses serviços podem ser usados ​​em toda a Adatum.

Em relação ao Microsoft Exchange, o CTO da Adatum solicitou que Holly revisasse algumas das funções administrativas básicas do Exchange Online relacionadas ao fluxo de emails e ao gerenciamento de destinatários. Como a função de administrador global inclui a função de administrador do Exchange, Holly pode executar todas as tarefas relacionadas ao Exchange.

Link: https://github.com/MicrosoftLearning/MS-100T00-Microsoft-365-Identity-and-Services/blob/master/Instructions/Labs/LAB_AK_04_Lab3_Ex1_Exchange_Online.md

# Exercício 3 - Revise os principais recursos do SharePoint Online
O CTO da Adatum ouviu falar muito sobre o Microsoft SharePoint Online e está interessado em implementá-lo na Adatum. No entanto, a segurança é a maior preocupação do CTO, que está preocupado se novos sites criados dentro da empresa podem ser mantidos seguros. O CTO encarregou Holly de revisar algumas das funções administrativas básicas do SharePoint Online para determinar se ele pode atender aos requisitos de segurança.

Link: https://github.com/MicrosoftLearning/MS-100T00-Microsoft-365-Identity-and-Services/blob/master/Instructions/Labs/LAB_AK_04_Lab3_Ex2_SharePoint_Online.md

# Exercício 4 - Criar um sistema de tíquetes no SharePoint
À medida que a Adatum inicia sua transição para o Microsoft 365 como sua solução de nuvem hospedada, eles desejam usar essa oportunidade para reduzir a quantidade de produtos de software de terceiros que usam atualmente. Isso os ajudará a atingir seu objetivo de reduzir as despesas gerais de TI. O CTO pediu a Holly Dickson, administradora corporativa da Adatum, para projetar uma solução que usa os serviços do Microsoft 365 para substituir o sistema de solicitação de serviços de TI de terceiros que a Adatum usa atualmente.

Como Holly está ocupada executando o projeto piloto do Microsoft 365 junto com suas outras responsabilidades administrativas, o CTO a autorizou a contratar um consultor de TI para projetar o novo sistema de tíquetes de solicitação de serviço. No entanto, ele não quer que o consultor tenha acesso a todo o sistema Adatum, então ele quer que Holly implemente “boas práticas de segurança” apenas fornecendo ao consultor acesso ao ambiente de projeto piloto de TI da Adatum.

Importante: colaboração com um usuário externo
No Laboratório 1, seu instrutor atribuiu a você o ID do sufixo do inquilino de um colega de classe. O ID de locatário do seu colega representará o consultor de TI que fará parceria com Holly Dickson na construção do novo sistema de tíquetes de solicitação de serviço da Adatum. Neste laboratório, você fornecerá o ID de locatário do seu colega com acesso ao novo sistema de tíquetes. Em um exercício do laboratório 1, você autorizou o acesso externo ao seu inquilino a partir da ID do inquilino deste aluno. Ao fornecer acesso externo a essa ID de sufixo de locatário, você e seu colega poderão colaborar por meio do Microsoft Teams ao configurar esse novo sistema de tíquetes de solicitação de serviço (você fará isso no próximo laboratório que trata do Teams).

No exercício de laboratório anterior, você criou um site de equipe do SharePoint chamado Serviços de TI. Ao desenvolver este site, você empregará boas práticas de segurança, limitando o acesso ao site para Holly e o ID do inquilino de seu colega (esse ID do inquilino representa o consultor de TI). Ao configurar o novo sistema de tíquetes de solicitação de serviço, você acessará o site usando a ID de locatário de seu colega para provar que o consultor de TI pode acessar o sistema. No próximo laboratório envolvendo o Microsoft Teams, você conversará com seu colega sobre o novo sistema de tíquetes. Lembre-se de que o aluno designado como seu consultor de TI também assumirá a função de Holly Dickson em seu próprio laboratório, e você assumirá a função de consultor de TI com outro aluno. Portanto.

Link: https://github.com/MicrosoftLearning/MS-100T00-Microsoft-365-Identity-and-Services/blob/master/Instructions/Labs/LAB_AK_04_Lab3_Ex3_Ticketing_System.md

# Exercício 5 - Revise os principais recursos do Microsoft Teams
Neste exercício, você aprenderá como gerenciar e configurar equipes por meio do centro de administração do Microsoft Teams.

Link: https://github.com/MicrosoftLearning/MS-100T00-Microsoft-365-Identity-and-Services/blob/master/Instructions/Labs/LAB_AK_04_Lab3_Ex4_Microsoft_Teams.md

# Exercício 6 - Revise o Power Platform Admin Center
À medida que a Adatum inicia sua transição para o Microsoft 365 como sua solução de nuvem hospedada, eles desejam aproveitar esta oportunidade para examinar a funcionalidade da Power Platform da Microsoft. Em sua função como Holly Dickson, administradora corporativa da Adatum, você foi solicitado a expandir seu projeto piloto do Microsoft 365 para incluir a plataforma de energia da Microsoft. Portanto, sua primeira tarefa para esse objetivo é se familiarizar com o centro de administração da Power Platform, que fornece um portal unificado para administradores gerenciarem ambientes e configurações para Power Apps, Power Automate e Power BI.

Link: https://github.com/MicrosoftLearning/MS-100T00-Microsoft-365-Identity-and-Services/blob/master/Instructions/Labs/LAB_AK_04_Lab3_Ex5_Power_Platform_admin_center.md

# Exercício 7 - Criar um Power App a partir de uma fonte de dados do SharePoint
Em um exercício anterior neste laboratório, Holly criou um sistema de tíquetes de solicitação de serviço para gerenciar as solicitações do service desk. O sistema de tíquetes consistia em um site de equipe do SharePoint intitulado Serviços de TI e uma lista do SharePoint dentro desse site intitulada Solicitações do Service Desk . Holly preencheu esta lista com os tíquetes de solicitação de serviço do antigo sistema de tíquetes da Adatum.

Em vez de fazer com que a equipe de suporte da Adatum use o SharePoint para inserir e gerenciar novos tíquetes de serviço, Holly prevê o uso de um Power App para executar essa função. Portanto, neste exercício, você criará um Power App que utiliza a lista de solicitações do Service Desk do SharePoint como fonte de dados para o aplicativo. Holly publicará e compartilhará o aplicativo com o consultor de TI para fins de teste como parte do projeto piloto da Adatum.

Link: https://github.com/MicrosoftLearning/MS-100T00-Microsoft-365-Identity-and-Services/blob/master/Instructions/Labs/LAB_AK_04_Lab3_Ex6_Power_App_from_SPdata.md

#  Exercício 8 - Criar um Power App do zero
No exercício anterior, você usou o Power Apps para criar automaticamente um aplicativo de tela da fonte de dados do SharePoint. Neste exercício, você criará um aplicativo semelhante do zero, usando a mesma lista do SharePoint como fonte de dados. O objetivo deste exercício é que você aprenda a criar um aplicativo do zero.

No exercício de laboratório anterior, quando o Power Apps criou o aplicativo para o sistema Service Desk Ticketing, ele criou automaticamente as seguintes telas usadas no aplicativo – a tela de navegação, a tela de detalhes e a tela de edição. Ao criar um aplicativo de tela do zero, você criará manualmente cada uma dessas telas:

Link: https://github.com/MicrosoftLearning/MS-100T00-Microsoft-365-Identity-and-Services/blob/master/Instructions/Labs/LAB_AK_04_Lab3_Ex7_Power_App_from_scratch.md

# Exercício 9 - Criar um fluxo usando o Power Automate
Em sua função como Holly Dickson, administradora corporativa da Adatum, você criou um novo sistema de tíquetes de service desk no SharePoint que consiste em um site de equipe intitulado Serviços de TI e uma lista do SharePoint intitulada Solicitações de Service Desk . Em seu esforço para implementar a Power Platform da Microsoft na Adatum, você criou um Power App que permite aos usuários inserir tíquetes de serviço usando o aplicativo em vez do SharePoint e também adicionou o aplicativo ao Microsoft Teams para que os usuários possam acessar o Power App por meio do Teams .

Como parte de seu projeto piloto da Power Platform, você agora deseja investigar como pode usar o Power Automate para melhorar seu novo sistema de emissão de tíquetes. Depois de revisar o antigo sistema de tickets da Adatum, você percebeu que a falta de comunicação em tempo real entre gerentes e clientes (seus usuários internos) era um fator chave para sua ineficácia. Para resolver esse problema, você decidiu criar e compartilhar um fluxo automatizado no Power Automate que envia automaticamente um email ao Administrador do MOD sempre que uma solicitação de serviço é criada ou modificada.

Link: https://github.com/MicrosoftLearning/MS-100T00-Microsoft-365-Identity-and-Services/blob/master/Instructions/Labs/LAB_AK_04_Lab3_Ex8_Power_Automate_flow.md

#  Exercício 10 - Criar uma política de DLP usando o Power Automate
Por motivos de segurança, os administradores geralmente desejam garantir que determinados dados sejam mantidos protegidos. O Power Platform permite que você crie políticas de prevenção contra perda de dados que definem quais conectores podem compartilhar dados de negócios específicos. Por exemplo, você pode não querer que os dados corporativos armazenados no SharePoint sejam publicados automaticamente em seu feed do Twitter por um fluxo do Power Automate.

A Power Platform usa grupos de dados como uma maneira simples de categorizar conectores em uma política DLP. Os três grupos de dados disponíveis são o grupo de dados comerciais, o grupo de dados não comerciais e o grupo de dados bloqueados.

Uma boa maneira de categorizar os conectores é colocá-los em grupos com base nos serviços centrados nos negócios ou centrados no uso pessoal aos quais eles se conectam no contexto de sua organização. Os conectores que hospedam dados de uso comercial devem ser classificados como comerciais e os conectores que hospedam dados de uso pessoal devem ser classificados como não comerciais. Todos os conectores que você deseja restringir o uso em um ou mais ambientes devem ser classificados como Bloqueados.

Quando uma nova política é criada, por padrão, todos os conectores são colocados no grupo Non-Business. A partir daí, eles podem ser movidos para Negócios ou Bloqueados com base em sua preferência. Para que um fluxo seja executado, todos os seus conectores devem estar em um ou outro grupo. Se seu fluxo tiver conectores em ambos os grupos, o fluxo será suspenso automaticamente e não será executado. Como todos os conectores são atribuídos por padrão ao grupo Não comercial , se você quiser incluir dados em seu fluxo, deverá adicionar todos os conectores usados ​​no fluxo ao grupo Somente dados comerciais.

Neste exercício, você criará uma política DLP que usa dois conectores - um conector do SharePoint e um conector do Office 365 Outlook. Para que o fluxo funcione que usa essa política DLP, você deve mover os dois conectores para o grupo de dados corporativos.

Link: https://github.com/MicrosoftLearning/MS-100T00-Microsoft-365-Identity-and-Services/blob/master/Instructions/Labs/LAB_AK_04_Lab3_Ex9_DLP%20Policy_Power_Automate.md


#  Laboratório 4 

# Exercício 1 - Preparar para sincronização de identidade
Como nos exercícios de laboratório anteriores, você assumirá o papel de Holly Dickson, administradora corporativa da Adatum Corporation. A Adatum assinou recentemente o Microsoft 365 e você foi encarregado de implantar o aplicativo no ambiente de laboratório virtualizado da Adatum. Neste laboratório, você executará as tarefas necessárias para gerenciar seu ambiente de identidade do Microsoft 365 usando o centro de administração do Microsoft 365 e o Windows PowerShell.

Durante este exercício, você configurará e gerenciará o Azure AD Connect. Você criará usuários locais e validará o processo de sincronização para que suas identidades sejam movidas para a nuvem. Algumas das etapas podem parecer familiares dos exercícios anteriores; entretanto, neste caso, eles são necessários para validar o processo de sincronização.

Link: https://github.com/MicrosoftLearning/MS-100T00-Microsoft-365-Identity-and-Services/blob/master/Instructions/Labs/LAB_AK_05_Lab4_Ex1_Prepare_Identity_Synch.md

# Exercício 2 - Implementar sincronização de identidade
Neste exercício, você habilitará a sincronização entre o Active Directory local da Adatum e o Azure Active Directory. O Azure AD Connect continuará a sincronizar quaisquer alterações delta a cada 30 minutos. Em seguida, você fará algumas atualizações de usuários e grupos e forçará manualmente uma sincronização imediata em vez de esperar que o Azure AD Connect sincronize automaticamente as atualizações. Você então verificará se as atualizações foram sincronizadas.

Importante : ao iniciar este exercício, você deve executar as quatro primeiras tarefas sem nenhum atraso entre elas para que o Azure AD Connect não sincronize automaticamente as alterações feitas nos objetos de identidade.

Link: https://github.com/MicrosoftLearning/MS-100T00-Microsoft-365-Identity-and-Services/blob/master/Instructions/Labs/LAB_AK_05_Lab4_Ex2_Implement_Identity_Synch.md

# Exercício 3 - Gerenciar o acesso seguro do usuário
Como Holly Dickson, administradora corporativa da Adatum, você foi solicitado pelo CTO da Adatum a implantar a Autenticação de Passagem (PTA) e o Bloqueio Inteligente do Azure AD como um meio de fortalecer o gerenciamento de senhas em toda a organização.

Link: https://github.com/MicrosoftLearning/MS-100T00-Microsoft-365-Identity-and-Services/blob/master/Instructions/Labs/LAB_AK_05_Lab4_Ex3_Manage_secure_user_access.md
