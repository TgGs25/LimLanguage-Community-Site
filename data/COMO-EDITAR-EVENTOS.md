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
  "time": "19:00 – 20:00",
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
  "date": "2026-09-10",
  "time": "16:00 – 17:00",
  "language": "en",
  "place": "online"
}
```

Para marcar um evento como já realizado, troque `"upcoming"` por `"done"`.

**Atenção:** um evento `"upcoming"` com `date` já passada vai sozinho para "Realizados" no site (o evento de hoje continua em "Próximos" até o dia seguinte). Mesmo assim, é boa prática trocar para `"done"`.

## Conferir depois de salvar

Abra o site com `?checar=1` no final do endereço (por exemplo, `eventos.html?checar=1`). Aparece uma caixa, só para quem usa esse endereço, listando os eventos que foram **ignorados** por erro (nome faltando, `status` escrito errado) e os que foram movidos para "Realizados" pela data. Se o arquivo todo estiver com erro de vírgula ou aspas, a caixa também avisa.

## Campos

| Campo | Obrigatório | O que colocar |
|---|---|---|
| `status` | sim | `"upcoming"` (próximo) ou `"done"` (realizado) |
| `name` | sim | Nome do evento (igual ao da planilha de eventos e ao da opção do formulário de check-in) |
| `language` | não | `"en"` (inglês), `"es"` (espanhol) ou `"pt"` (português). O site traduz o nome do idioma sozinho |
| `place` | não | `"online"`, `"presencial"` ou o nome do lugar (ex.: `"Sala 12"`) |
| `date` | não | No formato `ano-mês-dia`, ex.: `"2026-12-05"`. O site mostra a data por extenso no idioma do visitante |
| `time` | não | Horário, ex.: `"19:00 – 20:00"` |
| `link` | não | Link do encontro (só aparece em eventos próximos; precisa começar com `https://`) |
| `description` | não | Uma frase curta |

Campos opcionais podem ser apagados do bloco (apague a linha inteira, e confira a vírgula da linha anterior).

## Ordem

- Em **Próximos**, o site ordena por data (os que têm data primeiro).
- Em **Realizados**, do mais recente para o mais antigo (quando tem data).
