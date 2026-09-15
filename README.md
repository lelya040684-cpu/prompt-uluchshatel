# Улучшатель промптов по правилам Anthropic

Пишешь запрос к нейросети как попало, получаешь готовый промпт. Внутри правила из официального гайда Anthropic по промптам и из системного промпта Claude Fable 5.1.

Работает в ChatGPT, Claude, Gemini и Claude Code. Бесплатно, лицензия MIT.

## Что он делает

Запрос: `напиши пост про кофейню чтоб не скучно. кофейня Зерно в Ярославле, варим на альтернативе, есть веранда`

Ответ:

```
<контекст>
Кофейня «Зерно» в Ярославле. Варим кофе альтернативными способами. Есть веранда. [впиши: для кого пост, для постоянных гостей или новых]
</контекст>

<задача>
Напиши пост для Instagram, который зовёт зайти в кофейню.
</задача>

<формат>
До 70 слов, живым разговорным языком: пост читают с телефона между делами. Закончи вопросом к читателю, чтобы ему захотелось ответить в комментариях.
</формат>

<пример>
Утро на веранде, кофе на альтернативе и никакой спешки.
</пример>
```

Где фактов не хватает, агент ставит пометку `[впиши: …]` и ничего не выдумывает.

## Как установить

### ChatGPT, Gemini, Claude в браузере

1. Открой файл [`агент.txt`](агент.txt) и скопируй текст целиком.
2. Вставь его первым сообщением в новый чат.
3. Дальше пиши запросы как обычно.

Чтобы не вставлять каждый раз: в ChatGPT и Claude создай проект и положи текст в его инструкции, в Gemini создай свой Gem.

### Приложение Claude (скилл)

1. Скачай архив [prompt-uluchshatel.zip](https://github.com/lelya040684-cpu/prompt-uluchshatel/releases/latest/download/prompt-uluchshatel.zip).
2. Открой [Customize → Skills](https://claude.ai/customize/skills), нажми «+» → Create skill → Upload a skill и выбери архив.
3. Пиши в любом чате: «улучши промпт: …».

Для скиллов в настройках должно быть включено выполнение кода (Code execution).

### Claude Code

Скилл:

```bash
git clone https://github.com/lelya040684-cpu/prompt-uluchshatel.git
cp -r prompt-uluchshatel/prompt-uluchshatel ~/.claude/skills/
```

Агент (по желанию, работает в отдельном окне и возвращает только готовый промпт):

```bash
mkdir -p ~/.claude/agents && cp prompt-uluchshatel/agents/prompt-uluchshatel.md ~/.claude/agents/
```

Вызов: напиши «улучши промпт: …» или команду `/prompt-uluchshatel`.

## Откуда правила

- [Гайд Anthropic по промптам](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices)
- [Системный промпт Claude Fable 5.1](https://platform.claude.com/docs/en/release-notes/system-prompts/claude-fable-5-1)

## Автор

Разборы нейросетей и промпты: [t.me/alex_aicontent](https://t.me/alex_aicontent), Instagram [@alex.ai.content](https://www.instagram.com/alex.ai.content/).
