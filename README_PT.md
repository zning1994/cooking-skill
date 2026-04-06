# cooking.skill

> Se você não sabe o que cozinhar, comece dizendo o que quer comer e o que existe na geladeira.

`cooking.skill` é uma skill de cozinha que faz poucas perguntas úteis e depois entrega uma receita realmente executável.

Foco padrão:

- comida caseira chinesa
- técnica prática para cozinha doméstica
- tom vivo, mas normal

## O que faz

- recomenda o que cozinhar
- trabalha a partir de vontade ou dos ingredientes disponíveis
- responde diretamente dúvidas sobre pratos e técnicas
- inclui substituições, erros comuns e formas de salvar o prato

## Fluxo básico

Detecta automaticamente:

- `o que você quer comer`
- `o que você tem em casa`
- `como fazer ou corrigir este prato`

Quando necessário, pergunta no máximo duas coisas:

1. `para quantas pessoas`
2. `se há restrições, ingredientes faltando ou limites de habilidade`

## Saída padrão

- o que cozinhar
- por que essa opção combina
- o que você precisa
- como fazer
- pontos-chave
- onde costuma dar errado
- substituições ou resgates

## Instalação

```bash
mkdir -p .claude/skills
git clone https://github.com/zning1994/cooking-skill .claude/skills/cooking-skill
```

Instalação global:

```bash
git clone https://github.com/zning1994/cooking-skill ~/.claude/skills/cooking-skill
```

