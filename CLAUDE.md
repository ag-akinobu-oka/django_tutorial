# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 目的

2026年度の目標として、[Django公式チュートリアル（日本語版）](https://docs.djangoproject.com/ja/6.0/intro) を順番に完了する。

## Claudeの役割

チュートリアルを自分で進める中で、分かりにくい箇所や詰まった箇所の補助。コードを書くのではなく、概念の説明・原因の調査・疑問への回答がメイン。

## 開発環境セットアップ

```bash
# 仮想環境の作成・有効化
python -m venv .venv
source .venv/bin/activate

# Djangoのインストール
pip install django

# バージョン確認
python -m django --version
```

## よく使うコマンド

```bash
# 開発サーバーの起動
python manage.py runserver

# マイグレーション
python manage.py makemigrations
python manage.py migrate

# テストの実行（全体）
python manage.py test

# テストの実行（特定アプリ）
python manage.py test polls

# テストの実行（特定クラス・メソッド）
python manage.py test polls.tests.QuestionModelTests.test_was_published_recently_with_future_question

# Djangoシェル
python manage.py shell

# 管理ユーザーの作成
python manage.py createsuperuser
```

## Q&Aログ (ADR)

質問への回答は `.claude/adr/` にADR形式で記録する。

- ファイル名: `YYYYMMDD-NNN-質問の要約.md`
- テンプレートと運用ルールは `.claude/adr/README.md` を参照
- 質問一覧ビューア: `.claude/adr/index.html`（ブラウザで開く）
- **ADR追加のたびに** `index.html` の `QA_DATA` 配列を更新する
- **同じ質問が2回以上あった場合**: `index.html` の `DUPLICATES` 配列と `README.md` の特記事項テーブルに追記する

## 資料の出力形式

ユーザーへ見せる資料・まとめはすべて **HTML/JS/CSS** で作成する（スキル: `html-materials`）。

## チュートリアル構成

チュートリアルは `mysite/` プロジェクト配下に `polls/` アプリを作成する形で進む。

- `mysite/` — Djangoプロジェクトルート（`settings.py`, `urls.py`, `wsgi.py`）
- `polls/` — チュートリアル用アプリ（`models.py`, `views.py`, `urls.py`, `tests.py`）
- `templates/` — テンプレートファイル（`polls/` サブディレクトリ以下）
- `static/` — 静的ファイル（`polls/` サブディレクトリ以下）
