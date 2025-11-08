# Sprint 4 – Compliance, Quality Assurance & Tests ✅

Repositório dedicado **exclusivamente** à entrega da disciplina **Compliance, Quality Assurance & Tests**.  
Aqui estão consolidados os artefatos e evidências requeridos na Sprint 4.

---

## 📌 Escopo da Entrega

- **Parte A – Testes Manuais (Azure Boards)**

  1. Lista dos testes planejados _(peso 20%)_
     - 20 casos mapeados cobrindo Autenticação, Gestão de Motos, Gestão de Pátios e APIs REST.
  2. Dados de entrada para cada teste _(peso 20%)_
     - Valores controlados informados no campo `Action`/`Test Data`.
  3. Dados de saída esperados _(peso 20%)_
     - Resultados descritos na coluna `Expected result` de cada passo.
  4. Procedimento de teste _(peso 20%)_
     - Passo a passo completo com verbos no imperativo (Acessar, Preencher, Verificar…).

  > **Obs.:** Todos os dados de entrada/saída são pré-definidos (e-mail, placa, status, pátio etc.) e alinhados ao plano de release e às funcionalidades implementadas.

- **Parte B – Testes Automatizados (Postman)** 5. Pelo menos 4 casos automatizados _(peso 20%)_
  - Collection Postman cobre: Criar moto, Listar motos, Atualizar moto, Excluir moto e (opcional) Validar dados inválidos.

---

## 🔗 Links Entregues

| Item                                       | Link                                                                                         |
| ------------------------------------------ | -------------------------------------------------------------------------------------------- |
| Azure Boards – Test Plans                  | https://dev.azure.com/RM555871/Sprint%204%20–%20Azure%20DevOps                               |
| Vídeo – Configuração & Execução dos testes | https://youtu.be/<id-do-video>                                                               |
| Aplicação (Azure)                          | https://motovision-api-8077.azurewebsites.net                                                |
| Swagger                                    | https://motovision-api-8077.azurewebsites.net/swagger-ui.html                                |
| Coleção Postman                            | [`postman/MotoVision.postman_collection.json`](postman/MotoVision.postman_collection.json)   |
| Environment Postman                        | [`postman/MotoVision.postman_environment.json`](postman/MotoVision.postman_environment.json) |

---

## 🧭 Visão Geral dos Testes
- **Automação:** Scripts Postman em JavaScript salvam variáveis (`motoId`, `motoPlaca`) e validam respostas para cada cenário.

### Estrutura dos Testes Automatizados

1. `POST /api/motos` – cria moto e armazena ID/placa.
2. `GET /api/motos/todos` – garante retorno em array com ao menos 1 item.
3. `PUT /api/motos/id/{{motoId}}` – atualiza status e compara dados.
4. `DELETE /api/motos/id/{{motoId}}` – remove e limpa variáveis.
5. _(Opcional)_ `POST /api/motos` (payload inválido) – valida erro (400/404).


---

## 📦 Conteúdo deste Repositório

```
.
├── README.md                        # Este documento
├── Link vídeo testes
├── Link AzureDevOps
└── postman/
    ├── MotoVision.postman_collection.json
    └── MotoVision.postman_environment.json
```

---

## ▶️ Como Reproduzir

1. **Aplicação rodando em nuvem**.
2. Atualizar `base_url` no environment Postman (ex.: `https://motovision-api-8077.azurewebsites.net`).
3. Importar collection + environment e rodar via **Collection Runner** ou `newman`.
   ```bash
   newman run postman/MotoVision.postman_collection.json \
     -e postman/MotoVision.postman_environment.json \
     --insecure
   ```
4. Para testes manuais, acessar o Azure Boards no link informado e seguir os passos de cada test case.

Usuários padrão:

- `admin@teste.com / admin123`

---

## 👥 Equipe

- Eduardo Miguel Forato Monteiro · RM555871
- Cícero Gabriel Oliveira Serafim · RM556996
- Murillo Ari Ferreira Sant’Anna · RM557183

---

