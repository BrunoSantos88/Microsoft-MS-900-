# Autenticação versus autorização

- Autenticação
- Autorização
- Autenticação multifator
- Autenticação e autorização usando a plataforma de identidade da Microsoft

# Próximas etapas
Este artigo define a autenticação e a autorização. Ele também aborda rapidamente a autenticação multifator e como você pode usar a plataforma de identidade da Microsoft para autenticar e autorizar usuários em aplicativos Web, APIs Web ou aplicativos que chamam APIs Web seguras. Se você vir um termo com o qual não está familiarizado, veja nosso glossário ou nossos vídeos da plataforma de identidade da Microsoft que abrangem conceitos básicos.

# Autenticação
A autenticação é o processo de provar que você é quem diz ser. Isso é obtido pela verificação da identidade de uma pessoa ou de um dispositivo. Às vezes, a autenticação é abreviada para AuthN. A plataforma de identidade da Microsoft usa o protocolo OpenID Connect para processar a autenticação.

# Autorização
Autorização é o ato de conceder a uma parte autenticada a permissão para fazer algo. Ele especifica quais dados você tem permissão para acessar e o que pode fazer com esses dados. Às vezes, a autorização é abreviada para AuthZ. A plataforma de identidade da Microsoft utiliza o protocolo OAuth 2.0 para processar a autorização.

# Autenticação multifator
A autenticação multifator é o ato de fornecer um fator adicional de autenticação a uma conta. Ela costuma ser usada como proteção contra ataques de força bruta. Às vezes, o termo é abreviado como MFA ou 2FA. O Microsoft Authenticator pode ser usado como um aplicativo para lidar com a autenticação de dois fatores. Para obter mais informações, confira autenticação multifator.

Autenticação e autorização usando a plataforma de identidade da Microsoft
Criar aplicativos que mantêm as próprias informações de nome de usuário e senha gera uma carga administrativa alta quando você precisa adicionar ou remover usuários em vários aplicativos. Em vez disso, os aplicativos podem delegar essa responsabilidade a um provedor de identidade centralizado.

O Azure AD (Azure Active Directory) é um provedor de identidade centralizado na nuvem. A delegação de autenticação e autorização permite cenários como:

Políticas de acesso condicional que exigem que um usuário esteja em um local específico.
Autenticação multifator que exige que um usuário tenha um dispositivo específico.
Permitir que um usuário entre uma vez e seja automaticamente conectado a todos os aplicativos Web que compartilham o mesmo diretório centralizado. Essa capacidade é chamada de SSO (logon único) .
A plataforma de identidade da Microsoft simplifica a autorização e a autenticação para desenvolvedores de aplicativos, fornecendo identidade como um serviço. Ela dá suporte a protocolos padrão do setor e bibliotecas de software livre para diferentes plataformas para ajudá-lo a começar a codificar rapidamente. Ela permite que os desenvolvedores criem aplicativos que se conectam a todas as identidades da Microsoft e obtenham tokens para chamar o Microsoft Graph, acessar APIs da Microsoft ou acessar outras APIs que os desenvolvedores criaram.

# Este vídeo explica a plataforma de identidade da Microsoft e os conceitos básicos da autenticação moderna:


# Aqui está uma comparação dos protocolos que a plataforma de identidade da Microsoft usa:

OAuth versus OpenID Connect: a plataforma usa OAuth para autorização e OpenID Connect (OIDC) para autenticação. O OpenID Connect é desenvolvido com base no OAuth 2.0, portanto, a terminologia e o fluxo são semelhantes entre os dois. Você pode até mesmo autenticar um usuário (através do OpenID Connect) e obter autorização para acessar um recurso protegido que o usuário possui (através do OAuth 2.0) em uma solicitação. Para saber mais, confira Protocolos OAuth 2.0 e OpenID Connect e Protocolo OpenID Connect.
OAuth versus SAML: a plataforma usa o OAuth 2.0 para autorização e SAML para autenticação. Para obter mais informações sobre como usar os dois protocolos juntos para autenticar um usuário e obter autorização para acessar um recurso protegido, veja Plataforma de identidade da Microsoft e fluxo de declarações de portador SAML do OAuth 2.0.
OpenID Connect versus SAML: a plataforma usa o OpenID Connect e o SAML para autenticar um usuário e habilitar o logon único. A autenticação SAML é comumente usada com provedores de identidade, como os Serviços de Federação do Active Directory (AD FS), federados ao Microsoft Azure Active Directory. Portanto, é frequentemente usada em aplicativos corporativos. O OpenID Connect é comumente usado para aplicativos puramente na nuvem, como aplicativos móveis, sites e APIs Web.
