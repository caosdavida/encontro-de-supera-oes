# Encontro de Superações — GitHub Pages + Supabase

Esta versão não usa Flask. O site é 100% HTML/CSS/JavaScript e pode ser publicado no GitHub Pages.

O banco de dados e as fotos ficam no Supabase.

## 1. Criar o banco

Crie um projeto no Supabase.

Depois abra o **SQL Editor**, crie uma nova query e cole todo o conteúdo de `supabase.sql`.

Execute.

## 2. Pegar as chaves

No Supabase, abra as configurações da API do projeto e copie:

- Project URL
- Publishable/anon key

Não use a `service_role` key no site.

## 3. Configurar o site

Abra `index.html`.

Procure:

const SUPABASE_URL = "COLE_AQUI_SUA_SUPABASE_URL";
const SUPABASE_ANON_KEY = "COLE_AQUI_SUA_CHAVE_ANON";

Troque pelos dados do seu projeto.

## 4. Testar

Abra o `index.html` pelo navegador para testar.

Para uma experiência mais próxima da publicação, também pode usar uma extensão de servidor local.

## 5. Publicar no GitHub Pages

Crie um repositório no GitHub e coloque:

- index.html
- supabase.sql
- README.md

Depois vá em:

Settings → Pages → Deploy from a branch → main → /root

Salve.

O GitHub Pages publica arquivos estáticos. Ele não executa Python/Flask no servidor; por isso esta versão usa Supabase para o banco e armazenamento. 

## Como funciona

GitHub Pages
  ↓
index.html
  ↓
Supabase
  ├── banco de relatos
  └── fotos

Quando uma pessoa envia um relato, o JavaScript envia o texto para a tabela `relatos` e, se houver foto, envia a imagem para o bucket `fotos`.

## Atenção

A configuração inicial permite envio anônimo. Para um site público real, é recomendado adicionar autenticação/moderação, CAPTCHA e limites anti-spam antes de divulgar o endereço.
