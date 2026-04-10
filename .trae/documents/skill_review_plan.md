# Skill 审查计划

## 审查对象
- AI知识库-拆分-挪动/SKILL.md
- AI知识库-拆分-读取提炼/SKILL.md
- AI知识库-拆分-移动填充/SKILL.md

## 审查内容
1. 逻辑流程是否清晰
2. 操作步骤是否完整
3. 输入输出描述是否准确
4. 可能存在的逻辑错误
5. 改进建议

## 审查结果

### AI知识库-拆分-挪动/SKILL.md

#### 问题
- **逻辑错误**：步骤2描述为"如果存在,则创建目录YYYYMMdd"，逻辑错误，应该是"如果不存在则创建raw目录，然后创建YYYYMMdd子目录"
- **输入输出描述**：步骤5中，触发下一个skill时，输入应该是JSON格式，但当前描述为"输入为移动结果中的文件列表和状态信息"，需要明确是JSON格式

#### 改进建议
- 修正步骤2的逻辑描述
- 明确步骤5的输入格式为JSON

### AI知识库-拆分-读取提炼/SKILL.md

#### 问题
- **逻辑不清晰**：步骤3中，"提取JSON中提及的文件的内容"，但前面的skill输出是移动的文件列表和状态信息，需要明确如何从JSON中获取文件路径
- **操作步骤不完整**：步骤5中，需要确保wiki/summary目录存在，如果不存在需要创建
- **输入输出描述**：步骤7中，输入应该是JSON格式，但当前描述为"输入JSON格式的摘要文档的路径"，需要明确JSON的结构

#### 改进建议
- 明确如何从输入JSON中获取文件路径
- 添加创建wiki/summary目录的步骤
- 明确步骤7的JSON输入结构

### AI知识库-拆分-移动填充/SKILL.md

#### 问题
- **逻辑不清晰**：步骤4中，提到"按照中图法分类方法"，但没有具体说明如何实现，需要补充中图法分类的具体逻辑
- **逻辑不清晰**：步骤4中，"将每个核心概念的md文件移动到wiki/concept目录指定的末端目录下"，但没有说明如何确定"指定的末端目录"
- **输入输出描述**：输入是JSON格式，但没有明确JSON的结构，需要说明如何从中获取摘要文档的路径

#### 改进建议
- 补充中图法分类的具体实现逻辑
- 说明如何确定"指定的末端目录"
- 明确输入JSON的结构

## 改进计划

### [x] 任务1：修正 AI知识库-拆分-挪动/SKILL.md
- **Priority**：P1
- **Depends On**：None
- **Description**：修正步骤2的逻辑描述，明确步骤5的输入格式为JSON
- **Success Criteria**：文件内容逻辑正确，描述清晰
- **Test Requirements**：
  - `programmatic` TR-1.1：文件内容无语法错误
  - `human-judgement` TR-1.2：逻辑描述清晰，无歧义

### [x] 任务2：修正 AI知识库-拆分-读取提炼/SKILL.md
- **Priority**：P1
- **Depends On**：任务1
- **Description**：明确如何从输入JSON中获取文件路径，添加创建wiki/summary目录的步骤，明确步骤7的JSON输入结构
- **Success Criteria**：文件内容逻辑正确，描述清晰，操作步骤完整
- **Test Requirements**：
  - `programmatic` TR-2.1：文件内容无语法错误
  - `human-judgement` TR-2.2：逻辑描述清晰，操作步骤完整

### [x] 任务3：修正 AI知识库-拆分-移动填充/SKILL.md
- **Priority**：P1
- **Depends On**：任务2
- **Description**：补充中图法分类的具体实现逻辑，说明如何确定"指定的末端目录"，明确输入JSON的结构
- **Success Criteria**：文件内容逻辑正确，描述清晰，操作步骤完整
- **Test Requirements**：
  - `programmatic` TR-3.1：文件内容无语法错误
  - `human-judgement` TR-3.2：逻辑描述清晰，操作步骤完整

### [x] 任务4：验证改进后的skill文件
- **Priority**：P2
- **Depends On**：任务3
- **Description**：验证三个skill文件的逻辑流程是否清晰，操作步骤是否完整，输入输出描述是否准确
- **Success Criteria**：所有文件均已修正，逻辑流程清晰，操作步骤完整，输入输出描述准确
- **Test Requirements**：
  - `human-judgement` TR-4.1：所有文件逻辑清晰，无歧义
  - `human-judgement` TR-4.2：操作步骤完整，无遗漏
  - `human-judgement` TR-4.3：输入输出描述准确，格式明确