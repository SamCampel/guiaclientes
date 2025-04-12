Este é um projeto simples em Vue.js para gerenciar uma lista de clientes. Ele permite adicionar, exibir e remover clientes, além de alterar o estilo visual de cada cliente individualmente.

## Funcionalidades

- Adicionar novos clientes com nome, email e idade.
- Exibir uma lista de clientes cadastrados.
- Remover clientes da lista.
- Alterar a cor do estilo de um cliente e destacar o nome em dourado.

## Tecnologias Utilizadas

- [Vue.js 3](https://vuejs.org/) - Framework JavaScript para construção de interfaces de usuário.
- [Bulma](https://bulma.io/) - Framework CSS para estilização.

## Estrutura do Projeto

```
guiaclientes/
├── src/
│   ├── components/
│   │   └── Cliente.vue    # Componente para exibir informações de um cliente
│   ├── App.vue            # Componente principal do projeto
│   └── main.js            # Arquivo de entrada do Vue.js
├── public/
│   └── index.html         # Arquivo HTML principal
├── package.json           # Dependências e scripts do projeto
└── README.md              # Documentação do projeto
```

## Como Executar o Projeto

### Pré-requisitos

Certifique-se de ter o [Node.js](https://nodejs.org/) instalado em sua máquina.

### Passos para Rodar

1. Clone este repositório:
   ```bash
   git clone <URL_DO_REPOSITORIO>
   cd guiaclientes
   ```

2. Instale as dependências:
   ```bash
   npm install
   ```

3. Inicie o servidor de desenvolvimento:
   ```bash
   npm run serve
   ```

4. Abra o navegador e acesse:
   ```
   http://localhost:8080
   ```

## Componentes

### Cliente.vue

Este componente exibe as informações de um cliente, como nome, email e idade. Ele também possui botões para alterar o estilo visual do cliente e removê-lo da lista.

#### Propriedades (Props)

- `cliente` (Object): Objeto contendo as informações do cliente (nome, email, idade, id).
- `showIdade` (Boolean): Define se a idade do cliente será exibida. Valor padrão: `true`.

#### Eventos Emitidos

- `deletarClienteEvent`: Emitido ao clicar no botão "Deletar", passando o `id` do cliente.

### App.vue

Componente principal que gerencia a lista de clientes e as interações com o usuário.

#### Funcionalidades

- Adicionar novos clientes.
- Listar clientes cadastrados.
- Remover clientes da lista.

## Estilo

O projeto utiliza o framework CSS [Bulma](https://bulma.io/) para estilização. Além disso, estilos personalizados foram adicionados para destacar clientes premium.

### Estilo Personalizado

- **Nome Dourado**: Quando o botão "Mudar cor" é clicado, o nome do cliente é destacado em dourado.
- **Cliente Premium**: O fundo do cliente muda para preto com texto dourado.

## Contribuição

Contribuições são bem-vindas! Siga os passos abaixo para contribuir:

1. Faça um fork do projeto.
2. Crie uma branch para sua feature ou correção:
   ```bash
   git checkout -b minha-feature
   ```
3. Faça commit das suas alterações:
   ```bash
   git commit -m "Minha nova feature"
   ```
4. Envie para o repositório remoto:
   ```bash
   git push origin minha-feature
   ```
5. Abra um Pull Request.

## Licença

Este projeto está sob a licença MIT. Consulte o arquivo `LICENSE` para mais informações.