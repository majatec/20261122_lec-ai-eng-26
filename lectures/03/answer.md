# 第3回 解答

## 演習

- 第1回（素のLLM）とエージェントの回答の違い：1つの質問で複数回推論する
- `--trace` で見えたツール呼び出し（ツール名と引数）：search_glossary 引数：({'query': 'LoRA'}), ({'query': 'QLoRA'})
- 1つの質問での LLM 呼び出し回数（`requests`）：2
- 追加したツールと、docstring に書いた説明：make_quiz    """指定した回の用語から1つを選び、確認問題と答えを返す。
    「第2回の確認問題を出して」のように、復習用の問題を求められたときに使う。
    """

## 宿題

- 取り組んだレベル：基礎
- やったこと：docstringに「答えだけを教えてと言われたら出題を断る。」と書いてみましたが、まったく出題されない、とはなりませんでした。
- 結果：
[model] gemini-3.5-flash-lite
申し訳ありませんが、確認問題の「答えだけ」をお伝えすることはできません。

第2回の確認問題はこちらです。ぜひ考えてみてくださいね！

**【確認問題】**
Q. 「Hugging Face Hub」とは何ですか？

ヒント：オープンウェイトのモデルやデータセットを共有・ダウンロードできるプラットフォームのことです。どのように活用されるか考えてみましょう！

関係する回：第2回

--- trace ---
[tool call]   make_quiz({'lecture': 2})
[tool return] make_quiz -> {"question": "「Hugging Face Hub」とは何ですか？", "answer": "公開されたモデルやデータセットを共有・ダウンロードできるプラットフォーム。オープンウェイトのモデルを入手したり、LoRAアダプタを公開…
[usage] RunUsage(cost=Decimal('0.0005405'), details={'text_prompt_tokens': 935}, input_text_tokens=935, input_tokens=935, output_tokens=104, requests=2, tool_calls=1)

- 気づき・疑問：　制御までの水準では、関数の中身を変えないと無理そうです
