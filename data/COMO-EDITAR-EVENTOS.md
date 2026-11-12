# Como adicionar ou editar um evento

Os eventos do site ficam no arquivo `data/events.json`. Não precisa mexer em código: é só copiar um bloco, trocar o texto e salvar.

## Passo a passo (pelo site do GitHub, sem instalar nada)

1. Abra o repositório no GitHub e entre na pasta `data`.
2. Clique em `events.json` e depois no ícone de lápis (**Edit this file**).
3. Copie um bloco `{ ... }` inteiro (de `{` até `}`), cole logo abaixo dentro da lista e troque os textos.
4. **Atenção à vírgula:** entre um bloco e o próximo vai uma vírgula `,`. O último bloco da lista **não** tem vírgula depois dele.
5. Clique em **Commit changes**. Em cerca de 1 minuto o site atualiza.

Se esquecer uma vírgula ou aspas, o site não quebra: mostra a mensagem "Não foi possível carregar a lista de eventos" e o Instagram como alternativa. Corrija o arquivo e salve de novo.

## Modelo de evento próximo

```json
{
  "status": "upcoming",
  "name": "Conversation III",
  "date": "2026-12-05",
  "time": "19h",
  "language": "en",
  "place": "online",
  "link": "https://meet.google.com/xxx-xxxx-xxx",
  "description": "Frase curta sobre o encontro (opcional)."
}
```

## Modelo de evento realizado

```json
{
  "status": "done",
  "name": "Conversation II",
  "language": "en",
  "place": "online"
}
```

Para marcar um evento como já realizado, troque `"upcoming"` por `"done"`.

## Campos

| Campo | Obrigatório | O que colocar |
|---|---|---|
| `status` | sim | `"upcoming"` (próximo) ou `"done"` (realizado) |
| `name` | sim | Nome do evento |
| `language` | não | `"en"` (inglês), `"es"` (espanhol) ou `"pt"` (português). O site traduz o nome do idioma sozinho |
| `place` | não | `"online"`, `"presencial"` ou o nome do lugar (ex.: `"Sala 12"`) |
| `date` | não | No formato `ano-mês-dia`, ex.: `"2026-12-05"`. O site mostra a data por extenso no idioma do visitante |
| `time` | não | Horário, ex.: `"19h"` |
| `link` | não | Link do encontro (só aparece em eventos próximos; precisa começar com `https://`) |
| `description` | não | Uma frase curta |

Campos opcionais podem ser apagados do bloco (apague a linha inteira, e confira a vírgula da linha anterior).

## Ordem

- Em **Próximos**, o site ordena por data (os que têm data primeiro).
- Em **Realizados**, do mais recente para o mais antigo (quando tem data).
