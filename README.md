# django_tutorial
2026年度の目標設定の一部として、pythonのWebアプリケーションフレームワークDjangoのtutorialの完了を記録するためのリポジトリ。

## やること
- https://docs.djangoproject.com/ja/6.0/intro の各チュートリアルを完了する。

## 開発環境のセットアップ・起動方法

```bash
# 仮想環境の有効化
cd ~/goals/django_tutorial
source .venv/bin/activate

# 仮想環境がない場合は作成してから
python -m venv .venv
source .venv/bin/activate
pip install django

# 開発サーバーの起動
cd mysite
python manage.py runserver
```

ブラウザで http://127.0.0.1:8000/ にアクセスして動作確認。
