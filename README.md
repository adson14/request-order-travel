# Request Order Travel

## Introdução

Este é um sistema de solicitação e gerenciamento de viagens. O projeto conta com dois tipos de usuários: um administrador, que pode aprovar ou cancelar pedidos de viagens, e um usuário padrão, que pode realizar solicitações de viagem.

## Configuração e Execução

### Passo 1: Clonar o Repositório

```bash
git clone --recurse-submodules <url_do_repositorio>
```

Caso já tenha clonado sem submódulos, inicialize-os manualmente:

```bash
git submodule init
git submodule update
```

### Passo 2: Iniciar os Contêineres Docker

Dentro da pasta principal do repositório, execute o comando:

```bash
docker compose up -d --build
```

Ou, dependendo da versão do Docker:

```bash
docker-compose up -d --build
```

### Passo 3: Acessar o Sistema

Já existem dois usuários padrões cadastrados:

- **Administrador** (Pode aprovar ou cancelar solicitações de viagem):

  - Email: `admin@example.com`
  - Senha: `password`

- **Usuário Standard** (Pode realizar solicitações de viagem):
  - Email: `user@example.com`
  - Senha: `password`

> Outros usuários podem ser criados via API, mas essa funcionalidade ainda não está disponível na interface frontend.

## Fluxo do Sistema

1. O usuário faz login e solicita uma viagem.
2. O administrador, autenticado no sistema, aprova ou cancela a solicitação de viagem.

## Executando Testes

Para rodar os testes automatizados, siga os passos abaixo:

1. Liste os contêineres ativos:

   ```bash
   docker ps
   ```

2. Pegue o ID do contêiner `request-order-travel-app` e substitua no comando abaixo:

   ```bash
   docker exec -it <id_do_container> bash -c "cd infra && ./vendor/bin/pest && exec bash"
   ```

## Tecnologias Utilizadas

- Laravel
- Vue.js
- MySQL
- Docker
- PestPHP

## Arquitetura Utilizada

- Clean Architecture

## Funcionalidades

- Autenticação
- Controle de Permissões
- Cadastro de Solicitações de Viagem
- Gestão de Solicitações de Viagem (Aprovar/Cancelar)
- Notificações

## Observações

Este repositório foi construído com submódulos. Certifique-se de inicializá-los corretamente ao clonar o projeto.

---

Caso tenha alguma dúvida, sinta-se à vontade para abrir uma issue ou contribuir com o projeto!
