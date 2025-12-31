# AI4S Semantic Scholar

Academic paper search plugin powered by [ai4scholar.net](https://ai4scholar.net) API for Dify platform.

**Author**: ai4scholar  
**Repository**: [GitHub](https://github.com/literaf/dify-plugin-ai4s-semantic-scholar)  
**Support**: [GitHub Issues](https://github.com/literaf/dify-plugin-ai4s-semantic-scholar/issues) | WeChat: literaf

---

## Overview

- **Plugin Type**: Tool Plugin (Python)
- **Tools**: 11 tools for paper search, paper details, paper analysis, and author search
- **Output**: Text (Markdown format)

This plugin wraps the Semantic Scholar API via ai4scholar.net proxy, providing stable service with unified credit billing.

---

## Configuration

After installing the plugin in Dify, configure the following credentials:

| Credential | Required | Description |
|-----------|----------|-------------|
| `api_key` | ✅ Yes | Your ai4scholar.net API Key |

**Get API Key**: Visit [ai4scholar.net](https://ai4scholar.net) to register and obtain your API key.

---

## Tools

### Paper Search

| Tool | API Endpoint | Description |
|------|-------------|-------------|
| **Semantic Search** (`semantic_search`) | `GET /graph/v1/paper/search` | Search papers by relevance using natural language |
| **Title Search** (`title_search`) | `GET /graph/v1/paper/search/match` | Search papers by exact or partial title |
| **Bulk Search** (`bulk_search`) | `GET /graph/v1/paper/search/bulk` | Execute multiple search queries at once |

### Paper Details

| Tool | API Endpoint | Description |
|------|-------------|-------------|
| **Paper Detail** (`paper_detail`) | `GET /graph/v1/paper/{paper_id}` | Get detailed information for a single paper |
| **Multiple Papers Detail** (`multiple_papers_detail`) | `POST /graph/v1/paper/batch` | Get details for multiple papers at once |

### Paper Analysis

| Tool | API Endpoint | Description |
|------|-------------|-------------|
| **Paper Recommendations** (`paper_recommendations`) | `GET /recommendations/v1/papers` | Get recommended papers based on a given paper |
| **Paper Citations** (`paper_citations`) | `GET /graph/v1/paper/{paper_id}/citations` | Get papers that cite the given paper |
| **Paper References** (`paper_references`) | `GET /graph/v1/paper/{paper_id}/references` | Get reference papers of the given paper |

### Author Search

| Tool | API Endpoint | Description |
|------|-------------|-------------|
| **Author Search** (`author_search`) | `GET /graph/v1/author/search` | Search authors and get publication statistics |
| **Author Detail** (`author_detail`) | `GET /graph/v1/author/{author_id}` | Get author details (h-index, citation count, etc.) |
| **Author Papers** (`author_papers`) | `GET /graph/v1/author/{author_id}/papers` | Get papers published by an author |

---

## Parameters

### Semantic Search

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `query` | string | ✅ | Natural language search query |
| `limit` | number | ❌ | Number of results (1-100, default 10) |
| `year` | string | ❌ | Year filter (e.g., "2020", "2020-2024") |
| `fields_of_study` | string | ❌ | Field of study filter |
| `open_access_only` | boolean | ❌ | Only return open access papers |

### Paper Detail

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `paper_id` | string | ✅ | Paper ID (supports S2 ID, DOI, arXiv ID) |
| `include_citations` | boolean | ❌ | Include citing papers |
| `include_references` | boolean | ❌ | Include reference papers |

### Paper Recommendations / Citations / References

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `paper_id` | string | ✅ | Paper ID (supports S2 ID, DOI, arXiv ID) |
| `limit` | number | ❌ | Number of results (default 10-20) |

### Author Search

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `query` | string | ✅ | Author name |
| `limit` | number | ❌ | Number of results (1-20, default 5) |

### Author Detail / Author Papers

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `author_id` | string | ✅ | Semantic Scholar author ID |
| `limit` | number | ❌ | Number of results (for author_papers only) |

---

## Credits

Each API call consumes 1 credit. Batch operations are charged per actual API call.

To get more credits, visit [ai4scholar.net](https://ai4scholar.net).

---

## Links

- [ai4scholar.net](https://ai4scholar.net) - API Service
- [Semantic Scholar API Docs](https://api.semanticscholar.org/api-docs/)
- [Dify Plugin Documentation](https://docs.dify.ai/)

---

## License

MIT License

---

# 中文说明

基于 [ai4scholar.net](https://ai4scholar.net) API 的学术论文搜索插件。

## 功能

- **论文搜索**: 语义搜索、标题搜索、批量搜索
- **论文详情**: 单篇详情、批量详情
- **论文分析**: 推荐论文、引用分析、参考文献
- **作者搜索**: 作者查询、作者详情、作者论文

## 获取 API Key

访问 [ai4scholar.net](https://ai4scholar.net) 注册并获取 API Key。

## 联系支持

- 微信: literaf
- GitHub Issues: [提交问题](https://github.com/literaf/dify-plugin-ai4s-semantic-scholar/issues)
