# portfolio

## 概要

このプロジェクトは、C言語で汎用的な関数を含む独自のライブラリを作成するものです。標準Cライブラリの関数を再実装したり、リスト操作などの追加関数を開発したりすることを通じて、関数の仕組みを理解し、効果的に使用する方法を学ぶことを目的としています。このライブラリは、今後のC言語でのプロジェクトにおいて非常に役立つものとなります。

## プロジェクトの目的

* C言語における基本的な関数の理解を深める。
* メモリ管理（確保と解放）の重要性を学ぶ。
* 再利用可能なコードを作成する能力を養う。
* Makefileを使用したコンパイルプロセスの理解。
* コーディング規約に従った開発経験。

## 実装内容

### 標準ライブラリ関数

以下の標準Cライブラリ関数を `ft_` プレフィックスで再実装しました。

* `ft_isalpha`
* `ft_isdigit`
* `ft_isalnum`
* `ft_isascii`
* `ft_isprint`
* `ft_strlen`
* `ft_memset`
* `ft_bzero`
* `ft_memcpy`
* `ft_memmove`
* `ft_strlcpy`
* `ft_strlcat`
* `ft_toupper`
* `ft_tolower`
* `ft_strchr`
* `ft_strrchr`
* `ft_strncmp`
* `ft_memchr`
* `ft_memcmp`
* `ft_strnstr`
* `ft_atoi`
* `ft_calloc` (`malloc` を使用)
* `ft_strdup` (`malloc` を使用)

### 追加関数

標準ライブラリには含まれていない、または異なる形式で存在する以下の関数を開発しました。

* `ft_substr`
* `ft_strjoin`
* `ft_strtrim`
* `ft_split`
* `ft_itoa`
* `ft_strmapi`
* `ft_striteri`
* `ft_putchar_fd`
* `ft_putstr_fd`
* `ft_putendl_fd`
* `ft_putnbr_fd`

### リスト操作関数(ボーナスパート)

以下のリスト操作関数を実装しました。

* `ft_lstnew`
* `ft_lstadd_front`
* `ft_lstsize`
* `ft_lstlast`
* `ft_lstadd_back`
* `ft_lstdelone`
* `ft_lstclear`
* `ft_lstiter`
* `ft_lstmap`

## 技術的な詳細

* **言語 (Language):** C
* **コンパイル (Compilation):**
    * `Makefile` を使用し、`cc` と `-Wall -Wextra -Werror` フラグでコンパイルします。
    * Makefileには `$(NAME)`、`all`、`clean`、`fclean`、`re` のルールが含まれています。
    * ボーナス関数は `bonus` ルールでコンパイルされます。
    * ライブラリファイル `libft.a` は `ar` コマンドを使用してリポジトリのルートに作成されます。
* **コーディング規約 (Coding Norm):** プロジェクトは指定されたコーディング規約（Norm）に準拠して記述されています。
* **メモリ管理 (Memory Management):**
    * ヒープで確保されたメモリは適切に解放されます。メモリリークはありません。
    * `malloc` を使用する関数 (例: `ft_calloc`, `ft_strdup`, `ft_substr` など) では、メモリ割り当ての失敗時に `NULL` を返します。
* **制限事項 (Constraints):**
    * グローバル変数の使用は禁止されています。
    * より複雑な関数を分割するためのヘルパー関数は、スコープを適切なファイルに制限するために `static` 関数として定義されています。
    * すべてのファイルはリポジトリのルートに配置されています。
    * 未使用のファイルの提出は許可されていません。

## 使用方法

1.  リポジトリをクローンします。
    ```bash
    git clone [リポジトリURL]
    cd [リポジトリ名]
    ```
2.  ライブラリをコンパイルします。
    ```bash
    make
    ```
    ボーナスパートを含める場合:
    ```bash
    make bonus
    ```
3.  対象のCプロジェクトで `libft.h` をインクルードし、コンパイル時に `libft.a` をリンクします。
    ```c
    #include "libft.h"

    int main()
    {
        ft_putstr_fd("Hello from libft!\n", 1);
        return (0);
    }
    ```
    コンパイル例:
    ```bash
    cc -Wall -Wextra -Werror your_program.c -L. -lft -o your_program
    ```
