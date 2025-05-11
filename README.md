# law-ai-mvp
AIで行政書士の勉強をサポートするMVP
## ブランチ運用ルール

- `main`: 本番用の安定ブランチ（基本は手動でマージ）
- `develop`: 開発用の最新ブランチ。基本はこのブランチで作業
- `feature/*`: 各機能ごとの作業ブランチ（例：feature/setup-docker）

### ブランチ運用例

- 機能作成：`git checkout -b feature/quiz-generation`
- 完了後：Pull Request → `develop` にマージ
- リリース時：`develop` → `main` にマージ
# develop 上で動作確認が揃ったら
git checkout main
git merge --no-ff develop
git tag -a v0.1.0 -m 'First MVP release'
git push origin main --tags
git checkout -b hotfix/fix-login-bug main
# 修正コミット
git push origin hotfix/fix-login-bug
# PR → main & develop 両方へマージ
