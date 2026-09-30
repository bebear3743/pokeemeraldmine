# Step 3 Goals — pokeemerald-expansion 1.17.1

> Scope: 只定义“改什么/不改什么”。不写代码，不写脚本，不改 CI。
>
> 状态取值只有三种：`改` / `不改` / `待定`。
>
> 规则：任何一块标为“改”之前，先确认 Step 2 中该块的实际路径与入口符号。

## 0. 总体约束

- 版本基线：pokeemerald-expansion 1.17.1，Step 2 已冻结路径层。
- CI：冻结，不改 `.github/workflows/build.yml`。
- 训练家数据源：`src/data/trainers.party`。
- 冠军房现状：`TRAINER_WALLACE`，`TRAINER_STEVEN` 目前只用于 `MeteorFalls_StevensCave`。
- 改版目的：自玩，不发布，不追兼容，不追性能。

## 1. Intro 开场

- 状态：`待定`
- 若改，改动方向（一句话）：
- 关联 Step 2 路径：`src/intro.c`、`src/expansion_intro.c`、`src/data/graphics/intro_scene.h`
- 关联资源：`graphics/intro/`、`graphics/expansion_intro/`、`graphics/intro_frlg/`

## 2. Starter 初始精灵

- 状态：`待定`
- 若改，改动方向（一句话）：
- 关联 Step 2 路径：`src/starter_choose.c`、`include/starter_choose.h`
- 关联地图脚本：`data/maps/LittlerootTown_ProfessorBirchsLab/scripts.inc`
- 注意：入口是 `CB2_ChooseStarter` / `CB2_StarterChoose`，不是 `StarterChoose`

## 3. Rival 对手

- 状态：`待定`
- 若改，改动方向（一句话）：
- 关联 Step 2 路径：`data/maps/Route103/scripts.inc`、`data/maps/Route110/scripts.inc`、`data/maps/Route119/scripts.inc`
- 关联数据：`src/data/trainers.party`
- 关联资源：`data/scripts/rival_graphics.inc`

## 4. Gym 道馆

- 状态：`待定`
- 若改，改动方向（一句话）：
- 关联 Step 2 路径：`data/maps/*Gym*/scripts.inc`、`data/scripts/set_gym_trainers.inc`、`src/gym_leader_rematch.c`
- 若只改某几个道馆，列出具体道馆名：

## 5. Team Magma

- 状态：`待定`
- 若改，改动方向（一句话）：
- 关联 Step 2 路径：`data/maps/MtChimney/scripts.inc`、`data/maps/MagmaHideout_4F/scripts.inc`
- 关联数据：`src/data/trainers.party`（`TRAINER_MAXIE_*`）

## 6. Team Aqua

- 状态：`待定`
- 若改，改动方向（一句话）：
- 关联 Step 2 路径：`data/maps/SeafloorCavern_Room9/scripts.inc`、`data/maps/AquaHideout_*/scripts.inc`
- 关联数据：`src/data/trainers.party`（`TRAINER_ARCHIE`）

## 7. Steven / Champion

- 状态：`待定`
- 若改，改动方向（一句话）：
- 关联 Step 2 路径：`data/maps/EverGrandeCity_ChampionsRoom/scripts.inc`、`data/maps/MeteorFalls_StevensCave/scripts.inc`
- 关联数据：`src/data/trainers.party`（`TRAINER_STEVEN`）
- 注意：当前冠军房是 `TRAINER_WALLACE`。若目标是 Steven 冠军，本块必须标为“改”，且必须改冠军房脚本。

## 8. Battle 系统

- 状态：`待定`
- 若改，改动方向（一句话）：
- 关联 Step 2 路径：`src/battle_*.c`、`include/battle*.h`、`data/battle_scripts_*.s`、`test/battle/`
- 注意：这是 Expansion 改动集中区，非必要不动。

## 9. 冻结标准

- 八块全部从 `待定` 变为 `改` 或 `不改`。
- 每块标为“改”时，必须写出改动方向一句话，且关联路径已存在于 Step 2 清单。
- 本文件冻结后，才进入 Step 4（代码改动）。
