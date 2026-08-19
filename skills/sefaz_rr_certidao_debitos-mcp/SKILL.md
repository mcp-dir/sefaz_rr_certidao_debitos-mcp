---
name: sefaz_rr_certidao_debitos-mcp
description: Skill da REST API do SEFAZ RR: Certidão Negativa de Débitos na MCP.AI: 1 endpoint em /api/sefaz_rr_certidao_debitos. SEFAZ RR: Certidão Negativa de Débitos, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# SEFAZ RR: Certidão Negativa de Débitos — REST API skill

Você tem acesso à **SEFAZ RR: Certidão Negativa de Débitos** REST API na MCP.AI.

> SEFAZ RR: Certidão Negativa de Débitos, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/sefaz_rr_certidao_debitos
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/sefaz_rr_certidao_debitos/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/sefaz_rr_certidao_debitos/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `sefaz_rr_certidao_debitos_consultar`

SEFAZ RR: Certidão Negativa de Débitos, consulta em fonte oficial. _(POST /api/sefaz_rr_certidao_debitos/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `cnpj` | string | Não | Parâmetro de consulta "cnpj". |
| `cpf` | string | Não | Parâmetro de consulta "cpf". |
| `ie` | string | Não | Parâmetro de consulta "ie". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_sefaz_rr_certidao_debitos` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
