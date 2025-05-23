O ollama será acessível através do localhost, portanto através de scripts será possível conectar no ollama sem modificações.

### Alguns comandos interessantes

#### Iniciar container
```
docker compose up -d
```

ou

```
bash start-ollama.sh
```

#### Instalar um modelo usando a REST API (POST)
```
curl http://localhost:11434/api/create -d {"name": "<NOME_MODELO>", "from": "<ID DO MODELO USADO (NECESSÁRIO SE NÃO ESTIVER USANDO MODELFILE)>", "modelfile": "<ARQUIVO DE MODELO (OPCIONAL)>"}
```

Exemplo:
```
curl http://localhost:11434/api/create -d {"name": "gemma3:4b-it-q4_0", "from": "gemma3:4b-it-q4_0"}
```

#### Inferência em um modelo usando a REST API (POST)
```
curl http://localhost:11434/api/generate -d {"model": "<MODEL_NAME>", "prompt": "<SEU PROMPT>"}
```

Exemplo:
```
curl http://localhost:11434/api/create -d {"model": "gemma3:4b-it-q4_0", "prompt": "O que é uma llm?"}
```
