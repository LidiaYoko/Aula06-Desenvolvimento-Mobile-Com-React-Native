<p align="center">
  <img src="./assets/icon.png" alt="Ícone do Minhas Finanças" width="120" />
</p>

<h1 align="center">Minhas Finanças</h1>

<p align="center">
  Um aplicativo simples para registrar receitas e despesas, acompanhar o saldo e visualizar onde as transações aconteceram.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Expo-SDK%2057-000020?logo=expo" alt="Expo SDK 57" />
  <img src="https://img.shields.io/badge/React%20Native-0.86.3-61DAFB?logo=react" alt="React Native 0.86.3" />
  <img src="https://img.shields.io/badge/Plataformas-Android%20%7C%20iOS%20%7C%20Web-2c3e50" alt="Android, iOS e Web" />
</p>

## Sobre o projeto

O **Minhas Finanças** é um aplicativo de controle financeiro pessoal desenvolvido com React Native e Expo. Ele permite registrar movimentações do dia a dia e consultar um resumo das receitas, despesas e saldo diretamente no dispositivo.

O aplicativo também oferece recursos opcionais para anexar uma foto de comprovante e associar uma localização à transação. A interface está disponível para Android, iOS e Web.

## Funcionalidades

- **Boas-vindas:** apresentação inicial exibida no primeiro acesso.
- **Dashboard:** saldo, totais de receitas e despesas e lista das transações recentes.
- **Cadastro de transações:** registro de receitas e despesas com descrição, valor, categoria e data.
- **Categorias:** Alimentação, Transporte, Saúde, Lazer, Moradia, Salário e Outros.
- **Detalhes e exclusão:** consulta dos dados de uma transação e remoção com confirmação.
- **Relatório:** visualização resumida de receitas, despesas e saldo.
- **Localização opcional:** registro das coordenadas atuais do dispositivo ou escolha de um ponto no mapa.
- **Mapa de transações:** visualização dos registros que possuem localização.
- **Comprovante opcional:** captura de uma foto ou seleção de uma imagem da galeria.
- **Cotações:** consulta dos valores do dólar e do euro, com atualização automática a cada cinco minutos e opção de atualização manual.
- **Persistência local:** os dados das transações são armazenados no dispositivo, sem necessidade de criar uma conta.

<p align="center">
  <video src="https://github.com/user-attachments/assets/1b681678-04fc-4e15-a149-33744ec328ac" width="300" controls autoplay muted loop></video>
</p>

## Tecnologias

- [React Native](https://reactnative.dev/) e [Expo SDK 57](https://docs.expo.dev/versions/v57.0.0/)
- [React Navigation](https://reactnavigation.org/) para navegação por abas e pilha
- [AsyncStorage](https://react-native-async-storage.github.io/async-storage/) para persistência local
- [Expo Location](https://docs.expo.dev/versions/v57.0.0/sdk/location/) para localização em primeiro plano
- [Expo ImagePicker](https://docs.expo.dev/versions/v57.0.0/sdk/imagepicker/) para câmera e galeria
- [react-native-maps](https://github.com/react-native-maps/react-native-maps) no Android e iOS
- [Leaflet](https://leafletjs.com/) e [OpenStreetMap](https://www.openstreetmap.org/) na versão Web
- [React Native Paper](https://callstack.github.io/react-native-paper/) e [Expo Vector Icons](https://icons.expo.fyi/) entre as dependências da interface

## Requisitos

- Node.js e npm
- Um dispositivo com o aplicativo Expo Go, ou um emulador configurado para a plataforma desejada
- Para compilar e executar em simuladores nativos, as ferramentas de desenvolvimento correspondentes à plataforma (Android Studio para Android ou Xcode para iOS)

## Como executar

1. Clone este repositório:

   ```bash
   git clone https://github.com/LidiaYoko/Aula06-Desenvolvimento-Mobile-Com-React-Native.git
   ```

2. Entre na pasta do projeto:

   ```bash
   cd Aula06-Desenvolvimento-Mobile-Com-React-Native
   ```

3. Instale as dependências:

   ```bash
   npm ci
   ```

4. Inicie o Expo:

   ```bash
   npm run start
   ```

5. Abra o projeto no Expo Go lendo o QR code exibido no terminal ou na página do Expo. Também é possível iniciar diretamente um destino:

   ```bash
   npm run android
   npm run ios
   npm run web
   ```

> **Observação:** a disponibilidade de simuladores e de módulos nativos varia conforme o ambiente de desenvolvimento. Para usar câmera, mapas ou localização em um dispositivo, autorize as permissões solicitadas pelo sistema operacional.

## Permissões e conexão

- **Localização:** solicitada quando a opção “Minha localização” é usada para registrar uma transação.
- **Câmera e biblioteca de mídia:** utilizadas somente quando o usuário escolhe fotografar ou selecionar um comprovante.
- **Internet:** necessária para buscar as cotações e carregar os mapas e imagens de mapa. A consulta de cotações usa um serviço externo e pode falhar se o serviço ou a conexão estiver indisponível.

As coordenadas e os comprovantes são opcionais. Sem uma localização, a transação não aparece como marcador no mapa; sem comprovante, os demais dados da transação continuam disponíveis normalmente.

## Organização do projeto

```text
.
├── assets/                 # Ícones e imagens do aplicativo
├── components/             # Componentes reutilizáveis das telas
├── context/                # Estado global e persistência das transações
├── database/               # Módulo de banco SQLite
├── hooks/                  # Lógica de localização, comprovantes e cotações
├── routes/                 # Navegação por abas
├── screens/                # Telas do aplicativo
├── App.js                  # Composição dos providers e navegação
├── app.json                # Configuração do Expo e permissões nativas
├── eas.json                # Perfis de build do EAS
├── package.json            # Dependências e comandos
└── theme.js                # Cores, espaçamentos e estilos compartilhados
```

## Persistência de dados

No fluxo atual do aplicativo, o contexto em `context/TransacoesContext.js` salva e carrega as transações usando **AsyncStorage**. Os dados ficam no armazenamento local do aplicativo e não são sincronizados com uma conta ou serviço de nuvem.

O repositório também contém `database/db.js`, com funções e estrutura para SQLite, mas esse módulo não está conectado ao contexto usado pelas telas. Portanto, a presença desse arquivo não significa que as transações atuais estejam sendo gravadas no SQLite.

## Verificações disponíveis

Para executar o lint configurado no projeto:

```bash
npm run lint
```

## Licença

Consulte o arquivo [LICENSE](./LICENSE). Antes de publicar o repositório, confirme se a licença e a atribuição atualmente presentes nesse arquivo correspondem à licença que você pretende aplicar ao projeto.

---

Desenvolvido como projeto do Módulo 06 do Curso de Capacitação em Desenvolvimento Full Stack — ITEAM.
