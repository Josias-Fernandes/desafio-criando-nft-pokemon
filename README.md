
# Pokémon NFT Battle Game - PokeJFL

Este projeto implementa um jogo de batalha de Pokémon utilizando NFTs (Tokens Não Fungíveis) com o padrão **ERC-721**. Cada Pokémon é representado por um NFT, e os jogadores podem batalhar com seus Pokémons para aumentar seus níveis. Somente o proprietário do jogo pode criar novos Pokémons, e apenas o proprietário de um Pokémon pode usá-lo em batalhas.

## Funcionalidades

- **Cunhar (Mintar)** novos NFTs de Pokémon.
- **Batalhas** entre Pokémons, com a possibilidade de os vencedores aumentarem seu nível.
- **Transferência** de Pokémons entre diferentes usuários.

## Pré-requisitos

- **Remix IDE**: Ambiente de desenvolvimento online para contratos inteligentes Ethereum.
- **Metamask**: Carteira de criptomoedas usada para interagir com redes blockchain.
- **OpenZeppelin**: Biblioteca para contratos inteligentes, usada para herdar a implementação do **ERC-721**.

## Execução no Remix IDE

Siga os passos abaixo para executar e interagir com o contrato no Remix:

### 1. Acessar o Remix IDE

- Abra o navegador e acesse o [Remix IDE](https://remix.ethereum.org/).

### 2. Criar ou Importar o Contrato

- No Remix, crie um novo arquivo chamado `PokeJFL.sol` na pasta **Contracts**.
- Copie e cole o código do contrato fornecido no arquivo.

### 3. Instalar a Biblioteca OpenZeppelin

Para que o contrato funcione corretamente, é necessário importar a biblioteca OpenZeppelin para o Remix:

- No menu de arquivos, crie um arquivo chamado **remix-compiler.config** e adicione a seguinte linha:

  ```json
  {
    "remappings": [
      "@openzeppelin/=@openzeppelin/"
    ]
  }
  ```

- A OpenZeppelin será automaticamente importada ao compilar o contrato.

### 4. Compilar o Contrato

- Vá para a aba **Solidity Compiler** (ícone do compilador no lado esquerdo).
- Escolha a versão do compilador `0.8.0` ou superior, que corresponde à versão do Solidity usada no contrato.
- Clique em **Compile PokeJFL.sol**.
- Verifique se a compilação foi bem-sucedida.

### 5. Conectar-se à Metamask

- Certifique-se de que a extensão **Metamask** está instalada e configurada no seu navegador.
- Conecte-se a uma rede de teste, como **Rinkeby** ou **Goerli**, ou use o **Ganache** para uma blockchain local.
- Garanta que sua conta tenha fundos de teste para cobrir as transações (use faucets de teste se necessário).

### 6. Implantar o Contrato

- Na aba **Deploy & Run Transactions** (ícone de foguete), selecione o ambiente "Injected Web3" para conectar-se ao Metamask.
- Selecione o contrato **PokeJFL** na lista de contratos.
- Clique no botão **Deploy** para implantar o contrato na blockchain.

### 7. Criar Novos Pokémons

Após a implantação, o proprietário do jogo (que implantou o contrato) pode criar novos Pokémons usando o método `createNewPokemon`:

- Preencha os campos `name`, `to` (endereço do proprietário), e `img` (URL da imagem do Pokémon).
- Clique em **transact** para criar o Pokémon.

### 8. Batalhar com Pokémons

Somente o proprietário de um Pokémon pode batalhar com ele:

- Use o método `battle` e insira os IDs dos Pokémons atacante e defensor.
- O nível dos Pokémons será atualizado com base na batalha (o atacante ganha mais se vencer).

### 9. Transferir Pokémons

Use o método `safeTransferFrom` para transferir a posse de um Pokémon para outro endereço.

### 10. Visualizar e Monitorar Transações

Todas as transações, como a criação de Pokémons e batalhas, serão registradas na aba **Deploy & Run Transactions**.

## Métodos Principais

- **createNewPokemon(string memory _name, address _to, string memory _img)**: Cria um novo Pokémon NFT.
- **battle(uint _attackingPokemon, uint _defendingPokemon)**: Realiza uma batalha entre dois Pokémons.
- **safeTransferFrom(address from, address to, uint256 tokenId)**: Transfere um Pokémon de um endereço para outro.

## Recursos

- [OpenZeppelin ERC-721](https://docs.openzeppelin.com/contracts/4.x/erc721)
- [Remix IDE](https://remix.ethereum.org/)
- [Faucet Rinkeby para ETH de teste](https://faucet.rinkeby.io/)

## Licença

Este projeto está licenciado sob a licença **GPL-3.0**.
