エラーログ

2023/08/24
セクション12:メール送信  35.提携メールの送信方法 16:00付近のフォームから送信したところでエラーが発生しています。ここの前までのセッションのフォーム送信は問題なく行えていました。
emails.contact.adminが見つからない、とのエラーです。

原因：
admin.blade.phpのパス違い。
contactの中ではなく、emailsの中に入ってしまっていた。

resources
└── views
    └── emails
        └── contact
            └── admin.blade.php


memo admin.blade.php
{{ \Illuminate\Support\Facades\Auth::user()->name }}
{{ asset('storage/'.\Auth::user()->image) }}
