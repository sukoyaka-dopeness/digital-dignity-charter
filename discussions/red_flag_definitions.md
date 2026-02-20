# Red Flag Definitions — Open Discussion

This document is a working draft.
These definitions are **not finalized**.
They exist to start a conversation, not to end one.

All numeric thresholds listed here are provisional proposals.
Community consensus, research, and real-world testing
should determine the final values.

→ Please contribute via [Issues](../../issues) or Pull Request.

---

## English

### What is a Red Flag?

A Red Flag is a measurable signal that an interface
is designed against the user's interest.

Red Flags are not proof of malicious intent.
They are indicators that warrant scrutiny.

---

### Category 1: Unsubscribe / Cancellation Flows

**Proposed threshold: 3 or more clicks to complete cancellation**

Discussion points:
- Should confirmation dialogs count as a click?
- How do we account for legitimate security steps?
- Any cancellation process requiring contact by phone only
  should automatically qualify as a Red Flag — phone-only
  flows can be deliberately designed to be unreachable,
  creating an effective barrier through exhaustion.

Current proposal: Any cancellation flow requiring 3+ distinct
user decisions (not mere confirmations) is a Red Flag.
Phone-only cancellation is a Red Flag regardless of
the number of steps.

Status: **UNRESOLVED — seeking community input**

---

### Category 2: Consent and Close Buttons

**Proposed threshold: Asymmetric visual weight between
"Accept" and "Decline" options**

Discussion points:
- Pixel-based definitions are insufficient — screen resolution
  varies per user. Relative ratios or conceptual standards
  (e.g. "visually equivalent") are more robust.
- WCAG contrast ratio as a baseline is a candidate,
  but symmetry requirements go beyond accessibility standards.
- Buttons with overlapping or contradictory labels
  (e.g. "Cancel" vs. "Dismiss" in the same dialog) should
  also qualify — ambiguous labeling is a form of manipulation.
- What counts as "equivalent visual weight" requires
  formal definition.
- Ad close buttons are a significant source of deception:
  elements that appear to close an ad instead trigger
  the ad link. Close button position and shape varies
  across ads, deliberately creating confusion.
  Future standardization of close button shape and
  approximate position is recommended.

Current proposal: Accept and Decline options should be
visually equivalent in size, contrast, and placement.
Ambiguous or redundant button labels that obscure
user intent are also a Red Flag.
Any element designed to appear as a close/dismiss control
but functioning as an ad link is a Red Flag.

Future consideration: Industry-wide standardization of
close button shape and position across ad formats.

Status: **UNRESOLVED — pixel threshold definition needed,
relative ratio approach recommended.
Close button standardization: long-term goal, not yet defined.**


---

### Category 3: Privacy Settings Accessibility

**Proposed threshold: Settings requiring navigation through
3 or more separate screens to locate**

Discussion points:
- Should search functionality exempt a service?
- How do we handle mobile vs. desktop differences?
- Is burial inside general "Account Settings" a Red Flag?

Current proposal: Privacy controls should be reachable
within 2 navigation steps from the main settings page.

Status: **UNRESOLVED — seeking community input**

---

### Category 4: Visual Manipulation (Confirmshaming)

**Pattern: Decline options written to induce guilt or shame**

Examples of the pattern:
- "No thanks, I don't want to save money"
- "I prefer to stay uninformed"

Discussion points:
- Can this be objectively measured, or is it inherently subjective?
- Should tone analysis tools be part of verification?

Status: **UNRESOLVED — definition difficult to formalize**

---

### Category 5: Manipulative Default Selections

**Pattern: Pre-selected options that benefit the service
provider at the user's expense, without clear disclosure**

Examples of the pattern:
- Installer dialogs where the paid/premium version is
  pre-selected, with the free option requiring active
  de-selection
- Pre-checked boxes for newsletter subscriptions,
  data sharing, or additional purchases during checkout
- Trial periods that auto-convert to paid plans without
  prominent disclosure at sign-up

Discussion points:
- Is any pre-selection a Red Flag, or only undisclosed ones?
- How prominent must disclosure be to exempt a default?
- Should the burden of proof be on the service to demonstrate
  the default serves the user's interest?

Current proposal: Any default selection that financially
benefits the provider and requires active user action
to avoid, without clear and prominent disclosure at the
point of selection, is a Red Flag.

Status: **UNRESOLVED — disclosure prominence threshold needed**

---

### How to Contribute

These numbers need research, not opinion alone.

We welcome:
- Academic references on dark pattern measurement
- Regulatory definitions (FTC, GDPR, DSA) that could
  anchor thresholds
- Real-world testing data
- Counterarguments to proposed thresholds

→ Open an Issue with the category name in the title.

---
---

## 日本語

### レッドフラグとは何か？

レッドフラグとは、インターフェースがユーザーの利益に反して
設計されているという、測定可能なシグナルだ。

レッドフラグは悪意の証明ではない。
精査が必要であることを示す指標だ。

---

### カテゴリ1：退会・解約フロー

**暫定閾値：解約完了までに3クリック以上**

議論すべき点：
- 確認ダイアログはクリックとしてカウントするか？
- 正当なセキュリティ確認ステップはどう扱うか？
- 電話のみでの手続きが必要な場合は、
  ステップ数に関わらず自動的にレッドフラグとすべき——
  電話窓口は意図的に繋がりにくく設計できるため、
  疲弊による断念を狙った障壁になりうる。

現在の提案：3つ以上の独立したユーザー判断（単純な確認を除く）
を要求する解約フローをレッドフラグとする。
電話のみの解約は、ステップ数に関わらずレッドフラグとする。

ステータス：**未解決 — コミュニティの意見を求める**

---

### カテゴリ2：同意ボタンと閉じるボタン

**暫定閾値：「同意」と「拒否」の選択肢における視覚的重みの非対称性**

議論すべき点：
- ピクセル値による定義は不十分——ユーザーごとに画面解像度が異なる。
  絶対値ではなく相対比率、または「視覚的に同等」という
  概念的基準の方が適切。
- WCAGのコントラスト比をベースラインとする案はあるが、
  対称性の要件はアクセシビリティ基準を超える議論が必要。
- 同一ダイアログ内で意味が重複または矛盾するラベル
  （例：「キャンセル」と「取り消し」）も該当すべき——
  曖昧なラベリングは操作の一形態だ。
- 「同等の視覚的重み」の正式な定義が必要。
- 広告のクローズボタンは重大な欺瞞の温床になっている。
  閉じるように見えてタップすると広告リンクに飛ぶ要素、
  広告ごとに異なるクローズボタンの位置や形状が
  意図的な混乱を生んでいる。
  将来的にクローズボタンの形状と概ねの位置を
  業界横断で標準化することを推奨する。

現在の提案：同意と拒否の選択肢は、サイズ・コントラスト・
配置において視覚的に同等であるべき。
ユーザーの意図を不明瞭にする曖昧・重複したボタンラベルも
レッドフラグとする。
閉じる操作に見えて広告リンクとして機能する要素は
レッドフラグとする。

将来的な検討：広告フォーマット横断でのクローズボタンの
形状・位置の業界標準化。

ステータス：**未解決 — ピクセル閾値の定義が必要、相対比率アプローチを推奨。
クローズボタンの標準化：長期的目標、未定義。**

---

### カテゴリ3：プライバシー設定へのアクセス

**暫定閾値：設定を見つけるために3画面以上の
ナビゲーションが必要な場合**

議論すべき点：
- 検索機能があれば免除されるか？
- モバイルとデスクトップの違いはどう扱うか？
- 一般的な「アカウント設定」に埋め込まれている場合は該当するか？

現在の提案：プライバシー設定はメイン設定ページから
2ステップ以内で到達できるべき。

ステータス：**未解決 — コミュニティの意見を求める**

---

### カテゴリ4：視覚的操作（コンファームシェイミング）

**パターン：罪悪感や恥を誘発するように書かれた拒否選択肢**

パターンの例：
- 「いいえ、節約には興味ありません」
- 「情報を得ないままでいいです」

議論すべき点：
- これは客観的に測定できるか、それとも本質的に主観的か？
- トーン分析ツールを検証に組み込むべきか？

ステータス：**未解決 — 定義の形式化が困難**

---

### カテゴリ5：デフォルト選択の操作

**パターン：明確な開示なしに、ユーザーの不利益において
サービス提供者が利益を得るよう事前選択された選択肢**

パターンの例：
- インストーラーのダイアログで有料・プレミアム版が
  デフォルト選択され、無料版を選ぶには能動的な
  選択解除が必要な設計
- 購入フロー中に、メルマガ登録・データ共有・
  追加購入が事前にチェックされている
- 登録時に目立つ開示なく、試用期間が自動的に
  有料プランに移行する設定

議論すべき点：
- すべての事前選択がレッドフラグか、
  それとも開示がないものだけか？
- デフォルトを免除するために、開示はどの程度
  目立つ必要があるか？
- デフォルトがユーザーの利益になることを証明する
  責任はサービス側にあるべきか？

現在の提案：選択の時点で明確かつ目立つ開示なしに、
経済的にサービス提供者に有利で、ユーザーが
能動的に回避する必要があるデフォルト選択は
レッドフラグとする。

ステータス：**未解決 — 開示の目立ち度の閾値定義が必要**

---

### 貢献方法

これらの数値には、意見だけでなく調査が必要です。

歓迎するもの：
- ダークパターン測定に関する学術的参考文献
- 閾値の根拠となる規制上の定義（FTC、GDPR、DSA）
- 実世界のテストデータ
- 提案された閾値への反論

→ カテゴリ名をタイトルに含めてIssueを開いてください。
