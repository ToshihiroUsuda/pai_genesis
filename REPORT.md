# 説明資料

## 概要

- Genesisを用い、把持ロボットの強化学習を行う。
- Apple Silicon搭載Macに再利用容易な環境を構築する。

## 実行環境

| 項目                                                                                            | 環境                                         |
| ----------------------------------------------------------------------------------------------- | -------------------------------------------- |
| PC                                                                                              | MacBook Air (MacBookAir10,1)                 |
| チップ                                                                                          | Apple M1、8コア（高性能4コア + 高効率4コア） |
| メモリ                                                                                          | 8 GB                                         |
| OS                                                                                              | macOS 26.6.2                                 |
| アーキテクチャ                                                                                  | arm64 (Apple Silicon)                        |
| uv                                                                                              | 0.12.19                                      |
| Python                                                                                          | 3.12.7 (`.venv`)                             |
| PyTorch (`torch`)                                                                               | 2.14.1                                       |
| `torchaudio`                                                                                    | 2.11.0                                       |
| `torchvision`                                                                                   | 0.29.1                                       |
| `genesis-world`                                                                                 | 1.4.4                                        |
| `pymeshlab`                                                                                     | 2025.7.post1                                 |
| rsl_rl (GitHub: [leggedrobotics/rsl_rl](https://github.com/leggedrobotics/rsl_rl))              | `v5.5.1-5-ga87ef38` (`a87ef38`)              |
| Genesis (GitHub: [Genesis-Embodied-AI/Genesis](https://github.com/Genesis-Embodied-AI/Genesis)) | `v1.4.4-8-g105898fc` (`105898fc`)            |

## 実行コマンド

### 学習

```bash
cd Genesis
python examples/manipulation/grasp_train.py
```

### 評価

```bash
python examples/manipulation/grasp_eval.py -e grasp -r
```

## 工夫点

- 環境構築
  - docker上に環境構築を試みたが、X11 Forwarding が通らないため、Macのローカルに環境構築
  - 環境の再作成を容易にするためにuvでパッケージを管理
- 強化学習
  - 参考資料1をベースに、Genesisリポジトリのexamples/manipulationのサンプルを実行した

## 参考資料

1. hEnka「[Genesis] 1時間で4脚ロボットの強化学習の環境構築」Qiita, https://qiita.com/hEnka/items/cc5fd872eb0bf7cd3abc （閲覧日: 2026年10月16日）.
2. npaka「Genesis 入門 (1) - 事始め」note, https://note.com/npaka/n/n07b448c74613 （閲覧日: 2026年10月16日）.
3. ryosukematsuda「Genesis環境構築でつまづいたこと」Qiita, https://qiita.com/ryosukematsuda/items/16a08301b498d8207ff3 （閲覧日: 2026年10月16日）.
