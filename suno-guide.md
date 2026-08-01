# Suno への指示の出し方

Sunoには歌詞を入れる「Lyrics」欄と、曲調を指定する「Style of Music」欄がある。
発音・構成・テンポの調整は、歌詞そのものをいじるより「Style of Music」欄の指示文でコントロールするのが基本。

## 1. サビ(Chorus)から始めたい

歌詞(`lyrics/onomichi-song.md`)は既に `[Chorus]` が一番最初のセクションになっているので、歌詞の並び自体は対応済み。
それでもSunoは前奏(イントロ)を自動で付けがちなので、Style of Music欄に以下のような一文を足す。

```
no instrumental intro, vocals start immediately at 0:00 with the chorus hook
```

日本語で書きたい場合は
```
イントロなし、0秒から歌い出し、サビから開始
```
でも通じることが多い。それでもイントロが付く場合は、同じ歌詞・同じStyleのまま再生成(reroll)を数回試すのが早い。

## 2. 「おみち」ではなく「おのみち」と発音させたい

`だんがんおのみち` のように単語がベタ書きで連続していると、「ん」の直後の「お」が呑み込まれて「おみち」に聞こえがちになる。
今回、歌詞側を単語ごとにスペース区切りへ修正した:

```
しゅうまつ　だんがん　おのみち　りょこう〜
```

これでも崩れる場合の追加の手:
- 「おのみち」だけカタカナにしてみる: `オノミチ`(Sunoはカタカナの方が輪郭をはっきり歌う傾向がある)
- 「の」を強調したいなら中黒で区切る: `お・の・み・ち`
- 単語ごとに改行してリズムの区切りを明確にする(4語連呼のラップ感も出やすい)

```
しゅうまつ
だんがん
おのみち
りょこう〜
```

## 3. 早口(特に「おのみち」を速く)にしたい

歌詞本文に「(速く)」のような指示を書き込むと、歌詞として歌われてしまうことがあるため非推奨。
テンポ・フロウの指示はStyle of Music欄に書く。

```
fast-paced Japanese rap chant, rapid-fire double-time flow on the chorus hook, especially quick and punchy on "おのみち", auctioneer-style speed rap, izakaya chant energy, 140-150 BPM
```

日本語なら
```
早口のラップ調、サビは倍速テンポで畳み掛けるように、特に「おのみち」の部分は特に速く小気味よく
```

ポイント:
- 「特にこの単語だけ速く」は単語単位でSunoに正確に伝わるとは限らない。効かない場合は、その単語を含む行だけ短い改行にして密度を上げる(上記の改行案)、または生成後に何度かrerollして狙った発音のテイクを選ぶのが現実的。
- BPMや"double-time""auctioneer flow"のような具体的な音楽用語を入れると再現性が上がる。
- 歌詞・Styleを変えずにreroll(再生成)を繰り返すのがSunoでの発音・ノリ調整の基本ムーブ。一発で狙い通りになることは少ない。

## 4. Style of Music 欄のたたき台(今回の曲用)

```
uptempo Japanese group chant / rap hybrid, drunken izakaya road-trip energy,
no instrumental intro, vocals start immediately with the chorus,
fast-paced rap flow on the chorus hook (especially quick on "おのみち"),
playful and mischievous mood (secretly drinking whiskey disguised as coffee),
Hiroshima/Onomichi travel vibe, call-and-response chant, 140-150 BPM
```
