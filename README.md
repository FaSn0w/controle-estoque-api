﻿<div class="markdown prose w-full break-words dark:prose-invert light">
  <h1>CONTROLE-ESTOQUE-API</h1>
  <p>Esse projeto contém as rotas de um sistema de cadastro de produtos utilizando a framework Express.js em Node.js. As
    rotas permitem que o usuário realize as operações básicas de CRUD (Create, Read, Update e Delete) em um banco de
    dados MongoDB.</p>
  <h2>Instalação</h2>
  <p>Antes de utilizar as rotas, certifique-se de que o Node.js e o MySQL estejam instalados em sua máquina.</p>
  <ol>
    <li>Clone o repositório para sua máquina local:</li>
  </ol>
  <pre><div class="bg-black rounded-md mb-4">  </div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-sh">git <span class="hljs-built_in">clone</span> https://github.com/seu-usuario/seu-repositorio.git
</code></div></div></pre>
  <ol start="2">
    <li>Instale as dependências do projeto:</li>
  </ol>
  <pre><div class="bg-black rounded-md mb-4">  </div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-sh">npm install
</code></div></div></pre>
  <ol start="3">
    <li>
      <p>Configure o arquivo <code> config.js </code> com as informações do banco de dados MySQL.</p>
    </li>
    <li>
      <p>Inicie o servidor:</p>
    </li>
  </ol>
  <pre><div class="bg-black rounded-md mb-4">  </div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-sh">npm start
</code></div></div></pre>
  <h2>Utilização</h2>
  <p>As rotas disponíveis no sistema são:</p>
  <h3>Cadastrar um produto</h3>
  <pre><div class="bg-black rounded-md mb-4">   </div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-bash">POST http://localhost:3000/cadastroProdutos
</code></div></div></pre>
  <p>Envie um objeto JSON no corpo da requisição com as informações do produto a ser cadastrado. Exemplo:</p>
  <pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>json</span> </div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-json"><span class="hljs-punctuation">{</span>
  <span class="hljs-attr">"nome"</span><span class="hljs-punctuation">:</span> <span class="hljs-string">"Produto 1"</span><span class="hljs-punctuation">,</span>
  <span class="hljs-attr">"marca"</span><span class="hljs-punctuation">:</span> <span class="hljs-string">"Marca A"</span><span class="hljs-punctuation">,</span>
  <span class="hljs-attr">"qtd"</span><span class="hljs-punctuation">:</span> <span class="hljs-number">10</span><span class="hljs-punctuation">,</span>
  <span class="hljs-attr">"preco"</span><span class="hljs-punctuation">:</span> <span class="hljs-number">99.99</span>
<span class="hljs-punctuation">}</span>
</code></div></div></pre>
  <h3>Listar todos os produtos</h3>
  <pre><div class="bg-black rounded-md mb-4">   </div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-bash">GET http://localhost:3000/cadastroProdutos
</code></div></div></pre>
  <p>Retorna um array com todos os produtos cadastrados no banco de dados.</p>
  <h3>Listar produtos com paginação</h3>
  <pre><div class="bg-black rounded-md mb-4">   </div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-bash">GET http://localhost:3000/cadastroProdutos/pagina?itensPorPagina=10&amp;pagina=1
</code></div></div></pre>
  <p>Retorna um array com os produtos cadastrados no banco de dados, de acordo com a paginação definida pelos parâmetros
    "itensPorPagina" e "pagina". É necessário enviar os valores dos parâmetros na requisição.</p>
  <h3>Buscar produtos</h3>
  <pre><div class="bg-black rounded-md mb-4">   </div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-bash">GET http://localhost:3000/cadastroProdutos/busca?nome=&amp;marca=&amp;qtd=
</code></div></div></pre>
  <p>Retorna um array com os produtos cadastrados no banco de dados, de acordo com os parâmetros de busca "nome",
    "marca" e "qtd". É possível enviar apenas um dos parâmetros, ou uma combinação deles.</p>
  <h3>Atualizar um produto</h3>
  <pre><div class="bg-black rounded-md mb-4">   </div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-bash">PUT http://localhost:3000/cadastroProdutos/:<span class="hljs-built_in">id</span>
</code></div></div></pre>
  <p>Envie um objeto JSON no corpo da requisição com as informações atualizadas do produto a ser modificado. É
    necessário enviar o id do produto na URL da requisição. Exemplo:</p>
  <pre><div class="bg-black rounded-md mb-4"><div class="flex items-center relative text-gray-200 bg-gray-800 px-4 py-2 text-xs font-sans justify-between rounded-t-md"><span>json</span> </div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-json"><span class="hljs-punctuation">{</span>
  <span class="hljs-attr">"nome"</span><span class="hljs-punctuation">:</span> <span class="hljs-string">"Produto 1 Atualizado"</span><span class="hljs-punctuation">,</span>
  <span class="hljs-attr">"marca"</span><span class="hljs-punctuation">:</span> <span class="hljs-string">"Marca B"</span><span class="hljs-punctuation">,</span>
  <span class="hljs-attr">"qtd"</span><span class="hljs-punctuation">:</span> <span class="hljs-number">20</span><span class="hljs-punctuation">,</span>
  <span class="hljs-attr">"preco"</span><span class="hljs-punctuation">:</span> <span class="hljs-number">199.99</span>
<span class="hljs-punctuation">}</span>
</code></div></div></pre>
  <h3>Deletar um produto</h3>
  <pre><div class="bg-black rounded-md mb-4">   </div><div class="p-4 overflow-y-auto"><code class="!whitespace-pre hljs language-bash">DELETE http://localhost:3000/cadastroProdutos/:<span class="hljs-built_in">id</span>
</code></div></div></pre>
  <p>Exclui o produto com o id enviado na URL da requisição.</p>
</div>
