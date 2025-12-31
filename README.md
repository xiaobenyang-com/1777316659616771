# WHOIS查询服务 

一个基于Model Context Protocol (MCP)的WHOIS域名查询服务器，支持877+顶级域名和169个国家代码顶级域名的解析，提供全面的域名注册信息查询功能。
A WHOIS domain name query server based on Model Context Protocol (MCP), supporting the resolution of over 877 top-level domains and 169 country code top-level domains, and providing comprehensive domain name registration information query functions.## 工具列表 Tool List

本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。 本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。

| 工具 Tool   | 描述 Description         |
|-------|--------------------|
| whois_lookup | Look up domain information using WHOIS protocol (port 43). Queries authoritative WHOIS servers for domain registration details including registrar, registrant, dates, nameservers, and status. Supports 1,260+ TLDs. |
| refresh_whois_servers | Refresh the WHOIS server dictionary by fetching the latest TLD list from IANA. This updates the list of available WHOIS servers for domain lookups. Run this periodically to ensure the server list is up-to-date. |
| list_supported_tlds | List all supported TLDs (Top-Level Domains) that have WHOIS servers available. Returns the complete list of TLDs that can be queried. |


## 检查服务 ## Inspector

工具在线测试： [https://mcp.xiaobenyang.com/inspector/1777316659616771](https://mcp.xiaobenyang.com/inspector/1777316659616771)

Online Tool test [https://mcp.xiaobenyang.com/inspector/1777316659616771](https://mcp.xiaobenyang.com/inspector/1777316659616771)

## 服务配置 MCP Server Config


> #### 如何获取 XBY-APIKEY ？ How to get XBY-APIKEY ?
> 访问小笨羊科技网站 [https://xiaobenyang.com](https://xiaobenyang.com)，注册用户即可获得APIKEY
> Visit XiaoBenYang website [https://xiaobenyang.com](https://xiaobenyang.com), register and get the APIKEY.

### SSE
```json
{
  "mcpServers": {
    "WHOIS查询服务": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "sse",
      "url": "https://mcp.xiaobenyang.com/1777316659616771/sse"
    }
  }
}
```
### STREAMABLE HTTP
```json
{
  "mcpServers": {
    "WHOIS查询服务": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "streamable_http",
      "url": "https://mcp.xiaobenyang.com/1777316659616771/mcp"
    }
  }
}
```
### STDIO
```json
{
    "mcpServers": {
        "WHOIS查询服务": {
          "command": "npx",
          "args": [
            "-y",
            "xiaobenyang-mcp"
          ],
          "env": {
            "XBY_APIKEY": "<YOUR_XBY_APIKEY>",
            "mcpId": "1777316659616771",
          },
          "transport": "stdio"
        }
      }
}

```
