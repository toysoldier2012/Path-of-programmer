#springbatch



![[Pasted image 20231125095149.png]]

- `JobLauncher` 作业调度器
- `Job` 作业，需要执行的任务逻辑
- `Step` 作业步骤
- `ItemReader` 数据输入
- `ItemProcessor` 数据处理
- `ItemWriter` 数据输出
- `JobRepository` 持久化


@EnableBatchProcessing

JobLauncher
JobBuilderFactory
StepBuilderFactroy

Job
Step
Tasklet

# Job

JobInstance
JobExecution
JobParameters

参数获取

chunkContext
@StepScope
@Value

参数校验

JobParameterValidator
DefaultJobParametersValidator
CompositeJobParametersValidator

增量参数

JobParametersIncrementer
DailyTimestampParamIncrementer

作业监听

JobExecutionListener
@beforeJob
@afterJob

# Step