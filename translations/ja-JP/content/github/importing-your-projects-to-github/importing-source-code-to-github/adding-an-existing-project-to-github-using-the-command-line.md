---
title: コマンドラインを使った GitHub への既存のプロジェクトの追加
intro: '既存の作業を {% data variables.product.product_name %}に置けば、多くの素晴らしい方法で共有とコラボレーションができます。'
redirect_from:
  - /articles/add-an-existing-project-to-github/
  - /articles/adding-an-existing-project-to-github-using-the-command-line
  - /github/importing-your-projects-to-github/adding-an-existing-project-to-github-using-the-command-line
versions:
  free-pro-team: '*'
  enterprise-server: '*'
  github-ae: '*'
---

{% data reusables.repositories.migrating-from-codeplex %}

{% tip %}

**ヒント:** ポイントアンドクリック型のユーザインターフェースに慣れている場合は、プロジェクトを {% data variables.product.prodname_desktop %}で追加してみてください。 詳しい情報については *{% data variables.product.prodname_desktop %}ヘルプ* 中の[ローカルコンピュータから GitHub Desktop へのリポジトリの追加](/desktop/guides/contributing-to-projects/adding-a-repository-from-your-local-computer-to-github-desktop)を参照してください。

{% endtip %}

{% data reusables.repositories.sensitive-info-warning %}

{% mac %}

1. {% data variables.product.product_location %}上で[新しいリポジトリを作成](/articles/creating-a-new-repository)します。 エラーを避けるため、新しいリポジトリは*README*、ライセンス、あるいは `gitignore` で初期化しないでください。 これらのファイルは、プロジェクトを {% data variables.product.product_name %}にプッシュした後で追加できます。 ![[Create New Repository] ドロップダウン](/assets/images/help/repository/repo-create.png)
{% data reusables.command_line.open_the_multi_os_terminal %}
3. ワーキングディレクトリをローカルプロジェクトに変更します。
4. ローカルディレクトリを Git リポジトリとして初期化します。
  ```shell
  $ git init -b main
  ```
5. ファイルを新しいローカルリポジトリに追加します。 これで、それらのファイルが最初のコミットに備えてステージングされます。
  ```shell
  $ git add .
  # ローカルリポジトリにファイルを追加し、コミットに備えてステージします。 {% data reusables.git.unstage-codeblock %}
  ```
6. ローカルリポジトリでステージングしたファイルをコミットします。
  ```shell
  $ git commit -m "First commit"
  # 追跡された変更をコミットし、リモートリポジトリへのプッシュに備えます。 {% data reusables.git.reset-head-to-previous-commit-codeblock %}
  ```
7. {% data variables.product.product_name %} リポジトリの Quick Setup ページの上部で、{% octicon "clippy" aria-label="The copy to clipboard icon" %} をクリックしてリモートリポジトリの URL をコピーします。 ![リモートリポジトリの URL フィールドのコピー](/assets/images/help/repository/copy-remote-repository-url-quick-setup.png)
8. ターミナルで、ローカルリポジトリがプッシュされる[リモートリポジトリの URL を追加](/github/getting-started-with-github/managing-remote-repositories)してください。
  ```shell
  $ git remote add origin <em> &lt;REMOTE_URL> </em>
  # 新しいリモートを設定する
  $ git remote -v
  # 新しいリモート URL を検証する
  ```
9. {% data variables.product.product_location %} へ、ローカルリポジトリの[変更をプッシュ](/github/getting-started-with-github/pushing-commits-to-a-remote-repository/)します。
  ```shell
  $ git push -u origin main
  # ローカルリポジトリの変更を、origin として指定したリモートリポジトリにプッシュする
  ```

{% endmac %}

{% windows %}

1. {% data variables.product.product_location %}上で[新しいリポジトリを作成](/articles/creating-a-new-repository)します。 エラーを避けるため、新しいリポジトリは*README*、ライセンス、あるいは `gitignore` で初期化しないでください。 これらのファイルは、プロジェクトを {% data variables.product.product_name %}にプッシュした後で追加できます。 ![[Create New Repository] ドロップダウン](/assets/images/help/repository/repo-create.png)
{% data reusables.command_line.open_the_multi_os_terminal %}
3. ワーキングディレクトリをローカルプロジェクトに変更します。
4. ローカルディレクトリを Git リポジトリとして初期化します。
  ```shell
  $ git init -b main
  ```
5. ファイルを新しいローカルリポジトリに追加します。 これで、それらのファイルが最初のコミットに備えてステージングされます。
  ```shell
  $ git add .
  # ローカルリポジトリにファイルを追加し、コミットに備えてステージします。 {% data reusables.git.unstage-codeblock %}
  ```
6. ローカルリポジトリでステージングしたファイルをコミットします。
  ```shell
  $ git commit -m "First commit"
  # 追跡された変更をコミットし、リモートリポジトリへのプッシュに備えます。 {% data reusables.git.reset-head-to-previous-commit-codeblock %}
  ```
7. {% data variables.product.product_name %} リポジトリの Quick Setup ページの上部で、{% octicon "clippy" aria-label="The copy to clipboard icon" %} をクリックしてリモートリポジトリの URL をコピーします。 ![リモートリポジトリの URL フィールドのコピー](/assets/images/help/repository/copy-remote-repository-url-quick-setup.png)
8. コマンドプロンプトで、ローカルリポジトリのプッシュ先となる[リモートリポジトリの URL を追加](/github/getting-started-with-github/managing-remote-repositories)します。
  ```shell
  $ git remote add origin <em> &lt;REMOTE_URL> </em>
  # 新しいリモートを設定する
  $ git remote -v
  # 新しいリモート URL を検証する
  ```
9. {% data variables.product.product_location %} へ、ローカルリポジトリの[変更をプッシュ](/github/getting-started-with-github/pushing-commits-to-a-remote-repository/)します。
  ```shell
  $ git push origin main
  # ローカルリポジトリの変更を、origin として指定したリモートリポジトリにプッシュする
  ```

{% endwindows %}

{% linux %}

1. {% data variables.product.product_location %}上で[新しいリポジトリを作成](/articles/creating-a-new-repository)します。 エラーを避けるため、新しいリポジトリは*README*、ライセンス、あるいは `gitignore` で初期化しないでください。 これらのファイルは、プロジェクトを {% data variables.product.product_name %}にプッシュした後で追加できます。 ![[Create New Repository] ドロップダウン](/assets/images/help/repository/repo-create.png)
{% data reusables.command_line.open_the_multi_os_terminal %}
3. ワーキングディレクトリをローカルプロジェクトに変更します。
4. ローカルディレクトリを Git リポジトリとして初期化します。
  ```shell
  $ git init -b main
  ```
5. ファイルを新しいローカルリポジトリに追加します。 これで、それらのファイルが最初のコミットに備えてステージングされます。
  ```shell
  $ git add .
  # ローカルリポジトリにファイルを追加し、コミットに備えてステージします。 {% data reusables.git.unstage-codeblock %}
  ```
6. ローカルリポジトリでステージングしたファイルをコミットします。
  ```shell
  $ git commit -m "First commit"
  # 追跡された変更をコミットし、リモートリポジトリへのプッシュに備えます。 {% data reusables.git.reset-head-to-previous-commit-codeblock %}
  ```
7. {% data variables.product.product_name %} リポジトリの Quick Setup ページの上部で、{% octicon "clippy" aria-label="The copy to clipboard icon" %} をクリックしてリモートリポジトリの URL をコピーします。 ![リモートリポジトリの URL フィールドのコピー](/assets/images/help/repository/copy-remote-repository-url-quick-setup.png)
8. ターミナルで、ローカルリポジトリがプッシュされる[リモートリポジトリの URL を追加](/github/getting-started-with-github/managing-remote-repositories)してください。
  ```shell
  $ git remote add origin <em> &lt;REMOTE_URL> </em>
  # 新しいリモートを設定する
  $ git remote -v
  # 新しいリモート URL を検証する
  ```
9. {% data variables.product.product_location %} へ、ローカルリポジトリの[変更をプッシュ](/github/getting-started-with-github/pushing-commits-to-a-remote-repository/)します。
  ```shell
  $ git push origin main
  # ローカルリポジトリの変更を、origin として指定したリモートリポジトリにプッシュする
  ```

{% endlinux %}

### 参考リンク

- [コマンドラインを使用してリポジトリにファイルを追加する](/articles/adding-a-file-to-a-repository-using-the-command-line)
