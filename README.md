# leitura-desconstruindo-a-web

Comandos por capítulo

<h2>Capítulo 1</h2>

<h6>Ver quantos processos foram criados do chrome para requisicao:
</h6>
  <code>
ps xufa | grep [c]hromium | wc -l 19
</code>

<h2>Capítulo 2</h2>

<h6>Utilizando funcao getaddrinfo:
</h6>
  <code>
    ❯ python3 -c 'import socket;print(socket.getaddrinfo("desconstruindoaweb.com.br", "http"))'
  </code>
