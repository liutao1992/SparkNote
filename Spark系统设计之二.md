初步认识了 Spark 进程模型中的 `Driver` 和 `Executors`、以及它们之间的交互关系。Driver 负责解析用户代码、构建计算流图，然后将计算流图转化为分布式任务，并把任务分发给集群中的 Executors 交付运行。

