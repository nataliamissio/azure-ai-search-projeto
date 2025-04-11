# Azure Cognitive Search: Utilizando AI Search para Indexação e Consulta de Dados de Livros

Esse projeto foi desenvolvido com o objetivo de explorar o Azure Cognitive Search aplicando inteligência artificial na indexação e consulta de dados estruturados — neste caso, uma pequena base de livros.

Além de demonstrar a configuração técnica, usei esse projeto para aprofundar meu entendimento sobre buscas inteligentes e como esse tipo de ferramenta pode ser útil em aplicações do mundo real, como bibliotecas digitais, sistemas de recomendação e portais de conteúdo.

---

## 1. Criação do Repositório

Criei este repositório para registrar todo o processo: desde a preparação dos dados até a criação do índice no Azure e os testes de busca. Ele também funciona como parte do meu portfólio, mostrando minha familiaridade com soluções baseadas em nuvem e inteligência artificial.

---

## 2. Passo a passo para configurar a pesquisa

### Etapas que segui:

1. **Criação do Serviço no Azure**
   - Acesse o [Portal do Azure](https://portal.azure.com)
   - Criei um recurso do tipo *Azure Cognitive Search*
   - Optei pelo plano gratuito (F) para testes

2. **Preparação da Fonte de Dados**
   - Usei um arquivo JSON com 4 livros, contendo os campos:
     - `id`, `titulo`, `autor`, `descricao`, `genero`
   - Os dados foram simulados manualmente, mas poderiam vir de uma base real (SQL, Blob Storage, etc)

     Exemplo:
     ```json
     {
       "id": "1",
       "titulo": "Dom Casmurro",
       "autor": "Machado de Assis",
       "descricao": "Um romance clássico da literatura brasileira sobre memória e ciúme.",
       "genero": "Romance"
     }
     ```

3. **Criação do Index**
   - Configurei os campos no índice da seguinte forma:

     | Campo       | Tipo      | Searchable | Filterable | Facetable | Key |
     |-------------|-----------|------------|------------|-----------|-----|
     | id          | string    | ❌         | ✅          | ❌         | ✅  |
     | titulo      | string    | ✅         | ✅          | ❌         | ❌  |
     | autor       | string    | ✅         | ✅          | ✅         | ❌  |
     | descricao   | string    | ✅         | ❌          | ❌         | ❌  |
     | genero      | string    | ✅         | ✅          | ✅         | ❌  |

4. **Consulta no Search Explorer**
   - Após o índice estar populado, usei o Search Explorer para testar buscas como:
     - `"Tolkien"`
     - `"guerra mundial"`
     - Filtro: `genero eq 'Romance'`

---

## 3. Insights, Possibilidades e Aprendizados

### 🧠 Possibilidades de Uso:
- Catálogos digitais com busca inteligente
- Bibliotecas públicas ou escolares com sistema de indexação
- Integração com sistemas de recomendação
- Dashboard no Power BI com dados textuais indexados

### ✅ Aprendizados:
- A estrutura dos campos no índice impacta diretamente a experiência do usuário na busca
- Ferramenta poderosa e relativamente simples de configurar
- Cognitive Search pode ser potencializado com *AI Skills* como análise de sentimento, OCR, tradução, entre outros

---

## 4. Ferramentas que se beneficiam desse tipo de solução

- **Power BI**: pode se conectar ao índice e gerar dashboards com filtros dinâmicos por gênero, autor, etc
- **Aplicações Web**: podem usar o Search SDK ou REST API para fazer consultas em tempo real
- **Assistentes Virtuais / Chatbots**: podem consultar a base indexada para responder perguntas de usuários

---

## 5. Conclusão

Foi uma experiência muito válida trabalhar com o Azure Cognitive Search. Mesmo com uma base de dados pequena, já é possível visualizar o potencial de uso em aplicações reais. O próximo passo seria aplicar *AI enrichment* para expandir os dados com insights automáticos.

---

## Recursos e Links Úteis

- [Documentação Oficial do Azure Cognitive Search](https://learn.microsoft.com/en-us/azure/search/)
- [Tutorial de Quickstart com JSON](https://learn.microsoft.com/en-us/azure/search/search-get-started-portal)
- [Exemplo de uso com Power BI](https://techcommunity.microsoft.com/t5/azure-ai/building-a-power-bi-dashboard-with-azure-cognitive-search/)

---



