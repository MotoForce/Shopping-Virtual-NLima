# Imob Velocity 5.0 — Backend multiplayer

Este pacote é o servidor que torna o modo **Online** funcional entre aparelhos diferentes.

## Importante
GitHub Pages hospeda apenas arquivos estáticos. Ele pode hospedar a PWA, mas **não executa este servidor Node.js**.

O frontend e o backend devem ficar assim:

- PWA: `https://SEU-USUARIO.github.io/SEU-REPOSITORIO/`
- Backend: `https://SEU-BACKEND.exemplo.com`

No campo **Endereço do servidor multiplayer** do Imob Velocity, informe apenas a URL do backend.

## Teste obrigatório
Após publicar o backend, abra no navegador:

`https://SEU-BACKEND.exemplo.com/api/health`

A resposta deverá ser JSON semelhante a:

```json
{"ok":true,"app":"Imob Velocity","version":"5.0.0"}
```

Se essa URL não responder, o modo Online não poderá criar ou entrar em salas.

## Implantação em serviço Node.js

1. Crie um novo repositório apenas para este backend.
2. Envie os arquivos deste pacote.
3. No serviço de hospedagem, selecione ambiente Node.js.
4. Comando de inicialização: `npm start`.
5. O serviço deve fornecer HTTPS público e a variável `PORT` automaticamente.
6. Copie a URL HTTPS final e informe-a no campo **Endereço do servidor multiplayer** do jogo.

O arquivo `render.yaml` permite implantação por infraestrutura como código em plataformas compatíveis com esse formato. O `Dockerfile` permite implantação em qualquer serviço que aceite containers.

## Segurança e persistência
As salas ficam em memória e expiram após cerca de 12 horas de inatividade. Reiniciar o backend encerra as salas existentes. Para produção comercial de maior escala, recomenda-se persistência em banco de dados e autenticação.
