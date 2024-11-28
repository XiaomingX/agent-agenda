### agentagenda —— 为智能代理提供任务管理工具

#### 简介
`agentagenda` 是一款为智能代理设计的任务和议程管理工具，帮助你轻松创建、跟踪和管理任务。


### 安装

```bash
pip install agentagenda
```

### 快速开始

以下代码展示了如何创建一个任务并将其标记为已完成：

```python
from agentagenda import create_task, finish_task

# 创建任务
task = create_task("编写 README.md 文件")
print(task)

# 完成任务
finish_task(task)
```

### 功能介绍

#### 1. 创建任务

通过 `create_task` 方法创建一个新任务。你可以选择性地为任务指定计划和步骤。

```python
task = create_task("完成项目", plan="项目计划")
print(task)
```

#### 2. 列出所有任务

使用 `list_tasks` 方法查看所有正在进行的任务。

```python
tasks = list_tasks()
print(tasks)
```

#### 3. 搜索任务

使用 `search_tasks` 方法根据关键词搜索任务。

```python
tasks = search_tasks("项目")
print(tasks)
```

#### 4. 删除任务

通过 `delete_task` 方法删除任务。

```python
delete_task(task)
```

#### 5. 完成任务

将任务标记为已完成，使用 `finish_task` 方法。

```python
finish_task(task)
```

#### 6. 取消任务

如果需要取消任务，使用 `cancel_task` 方法。

```python
cancel_task(task)
```

#### 7. 获取任务 ID

通过 `get_task_id` 方法获取任务的 ID。

```python
task_id = get_task_id(task)
print(task_id)
```

#### 8. 处理任务计划

- 使用 `create_plan` 方法为任务创建计划。

```python
plan = create_plan("完成项目")
print(plan)
```

- 使用 `update_plan` 方法更新任务的计划。

```python
update_plan(task, "更新后的项目计划")
```

#### 9. 处理任务步骤

- 使用 `create_steps` 方法根据目标和计划创建步骤。

```python
steps = create_steps("完成项目", "项目计划")
print(steps)
```

- 使用 `add_step` 方法向任务中添加新步骤。

```python
add_step(task, "新增项目步骤")
```

- 使用 `finish_step` 方法将任务的某个步骤标记为完成。

```python
finish_step(task, "完成某步骤")
```

---

### 方法说明

#### `create_task(goal: str, plan: str = None, steps: dict = None) -> dict`
创建一个新任务，返回任务的字典表示。你可以选择性地为任务指定计划和步骤。

#### `list_tasks() -> list`
列出所有当前进行的任务。

#### `search_tasks(search_term: str) -> list`
根据搜索关键词查找相关任务。

#### `delete_task(task: Union[dict, int, str]) -> None`
删除指定任务，可以传递任务字典、任务 ID 或字符串 ID。

#### `finish_task(task: Union[dict, int, str]) -> None`
将指定任务标记为已完成。

#### `cancel_task(task: Union[dict, int, str]) -> None`
取消指定任务。

#### `get_task_id(task: Union[dict, int, str]) -> str`
获取指定任务的 ID。

#### `get_task_by_id(task_id: str) -> dict`
通过任务 ID 获取任务的字典表示。

#### `get_last_created_task() -> dict`
获取最近创建的任务。

#### `get_last_updated_task() -> dict`
获取最近更新的任务。

#### `get_current_task() -> dict`
获取当前任务。

#### `set_current_task(task: Union[dict, int, str]) -> dict`
设置指定任务为当前任务。

#### `create_plan(goal: str) -> str`
为指定目标创建计划。

#### `update_plan(task: Union[dict, int, str], plan: str) -> dict`
更新指定任务的计划。

#### `create_steps(goal: str, plan: str) -> list`
根据目标和计划创建任务步骤。

#### `add_step(task: Union[dict, int, str], step: str) -> dict`
向指定任务添加新步骤。

#### `finish_step(task: Union[dict, int, str], step: str) -> dict`
将指定任务的步骤标记为已完成。

#### `cancel_step(task: Union[dict, int, str], step: str) -> dict`
取消指定任务的某个步骤。
