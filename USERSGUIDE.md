微服务任务调度平台使用指南
===

  # 1.1 任务调度首页
 
  任务调度管理首页主要包括三大部分：调度器信息、调度次数、对接项目详情
  * 调度器信息：调度器中心调度器的数量
  * 调度次数：调度中心调度Job的历史累计总数
  * 对接项目详情：调度中心对接的项目组总数，Job总数
  
  ## 调度器信息
  
  点击`调度器信息`，显示资源分配详情界面，如下图所示:
  
  ![](docs/images/user-handbook_firstPage1.png)
  
  每台调度器有三个具体指标：
  * Job上限值：所能负载的Job动态阈值;
  * Job运行数量：该调度器当前运行的Job数量；
  * Job预警值：当调度器运行的Job数超过预警值时，会发邮件通知管理员。
  
  鼠标悬浮至某台调度器上方即可显示。
  
  ![](docs/images/user-handbook_firstPage02.png)
  
  ## 调度次数
  
  点击`调度次数`，即可显示调度器的调度详情，共计两个图表：
  
  * 调度器调度趋势图
  * 任务调度状态统计
  
  ![](images/user-handbook_firstPage2.png)
  
  ### 调度器调度趋势图
  
  `调度器调度趋势图`表示各个调度器执行Job或Task调度次数的实时数据统计，便于观察某段时间内调度器的调度状况。 
  
  * 通过下拉框可选择Job调度次数或Task调度次数；
  * 选上时间范围即可显示相应图表；
  * 图表下方为各个调度器具体实例，点击可显示或隐藏
  
  ### 任务调度状态统计
  
  `任务调度状态统计`表示所有调度器的历史调度信息
  
  * 可按Job或Task分别显示出异常和已完成的历史累计数据;
  * 选择时间区间后，可通过下拉框选择查看全部或某个调度器的任务调度详情；
  * 可通过下拉框选择Job或是Task任务调度详情；
  * 点击下方异常或已完成按钮，可显示或隐藏相应图线。
  
  ![](docs/images/user-handbook_firstPage2.png)
  
  
  ## 对接项目详情
  
  点击`对接项目详情`，会显示微服务任务调度平台对接的项目组详情，如下图示：
  
  ![](docs/images/user-handbook_firstPage3.png)
  
  * jobGroup：对接的项目组名称
  * Job数量：对接的项目组配置的Job数
  * Task数量：对接的项目组自动或手动配置的Task数
  * 预警邮箱：对接项目组的联系人列表
  
  便于管理员能够迅速了解调度中心对接项目组的整体情况。
  
  
  # 1.2 调度器管理
  
  点击左边栏中`调度器管理`，会进入调度器管理界面，默认显示资源分配详情界面,如下图所示：
  
  ![](docs/images/user-handbook_schedulerMg1.jpg)
  
  图中显示各个调度器简要信息，点击某个调度器(柱状图),会显示该调度器所抢占的Job详情列表：
  
  * jobKey：所配置的Job名称
  * 类型：配置Job的定时任务类型，分为Cron与fixRate两类
  * job类型值：Cron表达式
  * 预警邮箱：该Job配置的预警邮箱
  * 描述信息：描述该Job的功能信息
  
  便于管理员能够迅速发现某台调度器所抢占的Job详情。
  
  在该界面上方点击`调度器管理`，会显示如下界面，分为以下几项：
  
  ![](docs/images/user-handbook_schedulerMg2.png)
  
  * 工作调度器：
  
  该类调度器具有抢占和调度Job的能力。对某调度器进行下线操作，它会立即失去抢占Job的能力，其已经抢占的Job执行完毕后会自动释放，进而被其他调度器抢占，该调度器下线后会进入下线调度器列表中；工作调度器列表提供下线以及批量下线的功能；
  
  * 下线调度器：
  
  该类调度器进程仍然存活，但失去了抢占Job与参与调度的能力。对该类调度器执行上线操作，其会进入工作调度器列表，且开始具有抢占和调度Job的能力；下线调度器列表提供上线及批量上线的功能；
  
  * 离线调度器：
  
  该类调度器进程不再存活，当`下线调度器`进程死亡后，会自动进入离线调度器列表，该类调度器进程重新启动后，会自动进入下线调度器列表；离线调度器列表也提供删除及批量删除的功能；
  
  * 白名单：
  
  将某个IP加入白名单之后，其具有调用所有执行器实例的权限；白名单列表提供批量删除的功能，删除该IP后自动失去该权限
  
  
  # 1.3 调度监控

  点击左边栏`调度监控`，会出现调度监控界面，如下图所示：
  ![](docs/images/user-handbook_schedulerWc.png)
  
  * 标号1：表示任务概览，分别为准备中、正在运行中、已停止、异常停止的Job数，以及项目汇总数量，Task汇总数量和Job汇总数量。  
  
  * 标号2：输入项目组名可实现按项目组过滤；
  
  * 标号3：某个项目组的调度监控概览，包括该项目组的已激活Job数，异常停止Job数，Job总数以及Job列表详情；
  
  * 标号4：可直接关联到对应Job的运行日志详情，如下图所示：
  
  ![](docs/images/user-handbook_schedulerWc2.png)
  
  可通过日志详情查看该Job运行的详细信息，点击图中标识1中级联按钮，可关联中至所引用的Task日志信息，如下图所示：
  
  ![](docs/images/user-handbook_schedulerWc3.png)
  
  
  # 1.4 TASK管理
  
  点击左边栏中`TASK管理`项，显示Task管理界面，如下图所示：
  
  ![](docs/images/user-handbook_taskMg1.png)
  
  Task管理界面中，Task按项目组分组显示，主要提供Task的配置、修改与删除等功能。本界面Task包含两部分，一部分Task使用了sia-task-hunter组件，通过标准注解实现Task的自动抓取，该类Task不允许修改；另外一部分Task并未使用sia-task-hunter组件，由用户手动添加，该部分Task可以修改和删除。
  * 标识1：可以查看Task所属的项目组列表，点击某个项目组，可查看该项目组下的具体task列表；
  
  * 标识2：可添加task；
  
  * 标识3：查看、修改、连通性和删除动作；
  
  * 标识4：某一Task的执行器实例列表；
  
  * 标识5：按应用名称过滤(Job管理页过滤与此相同)；
  
  * 标识6：按Task名称过滤(Job管理页过滤与此相同)；
  
  
  ## 添加Task
  
  点击标识2`添加task`，弹出添加Task界面，如下图所示：
  ![](docs/images/user-handbook_taskMg5.png)
  
  * `项目名称`：非管理员用户只能从下拉列表中选择项目名称，后台管理员可以手动录入添加，项目名称只能包含数字、字母、下划线和中划线；
  
  * `应用名称`：非管理员用户只能从下拉列表中选择应用名称，后台管理员可以手动录入添加，项目名称只能包含数字、字母、下划线和中划线；
  
  * `HTTP_PATH`：以左斜杠`/`为前缀，其余字符可为英文、数字、下划线，且路径不能包含右斜杠`\`；
  
  * `是否配置参数`： 该Task是否需要参数；
  
  * `描述`：一般为该Task的业务功能描述；
  
  * `IP:PORT`：可以添加多个，不可重复，每个`IP:PORT`必须可用（可通过`TELNET`访问）；每次输入一组`IP:PORT`点击右边的添加，通过后再添加下一个。如果是域名，请保证域名可用（能够`PING`通）
  
  ## 查看
  
  点击`查看`,可查看该Task是否被某个Job引用
  
  ## 修改Task
  
  点击`修改`,弹出修改Task界面如图所示：
  
  ![](docs/images/user-handbook_taskMg4.png)
  
  只能修改手动添加的任务中以下几项：`是否配置参数`、`描述`和`IP:PORT`。
  
  ## 删除Task
  
  点击`删除`,可将Task删除，如果Task被Job引用，则不能删除。
  
  ## Task连通性
  
  点击`连通性`进入联通性测试界面，如下图所示：
  
  ![](docs/images/user-handbook_taskMg3.png)
  
  `连通性`：对于使用了sia-task-hunter组件，通过标准注解实现自动抓取的Task而言,sia-task-hunter加入了权限控制，不在此权限内的IP不能调用该Task，如需测试该Task是否可以正常工作（仅限POST方式），需在此界面测试，因此称之为连通性。
  
  * `测试地址`:该Task的执行器实例集群，可选择其中某一个进行测试；
  
  * `测试参数`:该Task的执行器输入参数；
  
  * `response`: 该Task的执行器返回值
  
  点击`测试`，观察`response`值，即可测试该Task连通性
  
 
  # 1.5 JOB管理
 
  Job管理界面提供添加、修改、删除以及针对Job触发相关的操作；
  ## 页面概览
  通过点击左侧列表`Job管理`进入Job管理界面，如下图所示：
  
  ![user-handbook_jobMg1](docs/images/user-handbook_jobMg1.png)
  
  * 标识1：`项目名称`：假设当前用户拥有多个项目组的使用权限则显示全部（默认显示当前用户所在的项目组），点击下拉列表会显示所拥有的项目组列表，以供筛选/过滤Job使用。
  
  * 标识2：`添加Job`按钮，用户可通过点击此按钮进行Job的新增配置。
  
  * 标识3：`Task信息`，通过点击该按钮可查看当前Job的Task配置信息；`状态查看`：鼠标移至此处则会显示当前Job的运行时状态（状态：已停止/准备中/正在运行/异常停止）。
  
  * 标识4：针对当前Job的相关操作；`配置Task`：进行Job的Task配置；`修改Job`：修改Job相关参数；`状态操作`：该按钮是一个包含多个操作的下拉菜单，可针对当前Job进行相关操作；`级联设置`：设置不同Job的级联关系。
  
  ## 新增Job
  
  点击`添加Job`按钮，页面会弹出如下图示：
  
  ![user-handbook_jobMg2](docs/images/user-handbook_jobMg2.png)
  
  * `Job_Group` ：选择Job归属的项目组，可选列表中一般包含多个项目组；默认是随机显示当前用户所拥有权限的项目组其中之一，可通过点击此处进行选择所添加Job的归属。
  
  * `Job_Key`：Job唯一标识,以Job_Group为前缀；用户可输入自已定义的名称来标识此Job。
  
  * `Job类型`：Job的类型：当前版本支持两种模式。
  1. TRIGGER_TYPE_CRON （固定时刻，后续输入CRON表达式）；
  
  ![user-handbook-cron](docs/images/user-handbook-cron.png)
  
  2. TRIGGER_TYPE_FIXRATE ：代表任务按约定的时间开始执行，并且可以设置总的执行次数，以及两次执行之间的时间间隔。如果输入次数为0 则代表无穷大。
  
  ![user-handbook-fixrate](docs/images/user-handbook-fixrate.png)
  
 
  * `Job类型值`：针对不同的Job类型，输入合理的参数值。
  
  *`预警邮箱(前缀)`：任务失败、任务无法调度等情况，系统自动发邮件通知相关使用方。建议配置成项目组的邮箱，或者使用者的公司邮箱，不建议使用非公司邮箱账户。输入预警邮箱前缀，多个请用邮箱全程并以英文逗号隔开。
  
  * `描述`：Job 描述信息；
  
  正确填写上述信息，然后点击 `添加` 按钮，进行确认。此时再次选择所添加Job的项目组会显示。
  ## 修改Job
  可修改`Job`的类型、类型值，预警邮箱、描述等信息。界面同`新增Job`一致。当`Job`处于运行状态时，不可以修改。
  
  ## 配置Task
  
  ![user-handbook-task-config](docs/images/user-handbook-task-config.png)
  
  ### 添加Task
  点击`配置Task`按钮，页面会弹出如下图示：
  
  ![user-handbook-task-add](docs/images/user-handbook-task-add.png)
  
  * Task信息：图示左侧列表显示为当前用户权限匹配的Task信息；不同的颜色区分所归属的项目组不同。可通过`拖拽`的方式选择所需的`Task`，拖拽至右边空白区域，则代表选择该`Task`。可以拖拽多个`Task`。顶部输入框提供Task筛选功能。
  
  ### 移除Task
  点击`task`图标上面的移除按钮即可移除。
  
  ### 配置`Task`的依赖关系
  * Task信息配置图：选择的`Task`拖拽完成，则可通过连线的方式配置`Task`的依赖关系。如下图所示：
  ![user-handbook-task-configing](docs/images/user-handbook-task-configing.png)
  
  
  说明：
  （1）起始`Task`的运行时机为Job触发时进行唤起。
  （2）后置`Task`的运行时机为前置`Task`运行完成，当存在多个前置`Task`时，则所有的前置`Task`均运行完成后才会唤起后置`Task`。
  
  #### Task运行时参数配置
  * Task运行时参数配置：`Task`的依赖关系配置完成后，可进一步配置每个Task的运行时参数。
  
  ![user-handbook-task-configparam](docs/images/user-handbook-task-configparam.png)
  
  
  点击红色框图中的`编辑`按钮，页面会弹出如下图示：
  
  ![user-handbook-task-configparaming](docs/images/user-handbook-task-configparaming.png)
  
  * Task_参数类型：配置`Task`的参数来源，因部分`Task`选择的参数类型为`FROM_TASK`，因此需要在配置`Task`列表界面中设置`Task`的参数来自于哪个`Task`（必须为该`Task`的前置`Task`之一）；
  
  * Task_参数值：根据 `Task_参数类型`，进行合理配置对应的参数即可。（Task参数类型选择`FROM_UI`，输入Task能解析的JSON串，最多255字符）。
  
  * 过期时间(s)：设置Task ReadTimeOut的大小，单位为秒。
  
  * Task_选取实例策略：目前支持两种策略
  （1）随机（从可选的列表中，随机选择实例，即IP+端口）；
  （2）固定IP（指定实例，随后需要从可选列表中人工指定实例）。
  
  * Task_调用失败策略：目前支持四种策略可供配置
  （1）STOP（停止策略，调用失败则整个Job停止，不再执行后续Task）；
  （2）IGNORE（忽略策略，调用失败则跳过该Task，继续执行后续Task）；
  （3）TRANSFER（转移策略，选取该Task的其他实例执行，如果依然失败，则使用停止策略）；
  （4）MULTI_CALLS_TRANSFER（多次调用再转移策略，重复调用该Task多次，如果依然失败，则使用转移策略）。
  
  至此Job的task信息配置完成，点击提交确认。点击`Job管理界面`的`Task信息`按钮可查看当前所配置的Task依赖关系信息。
  
  ## 级联设置
  * `级联设置`：设置不同Job的级联关系。如果存在两个作业（`Task`）需要存在逻辑前后关系，同时后置任务也需要一定的时间关系，可使用该功能进行实现。将两个独立的作业（`Task`）封装为两个Job并设置独立的运行时间。然后对两个Job进行级联设置。
  
  ![user-handbook-task-configplan](docs/images/user-handbook-task-configplan.png)

  
  # 1.6 调度日志
  
  点击左边栏`调度日志`，进入调度日志界面，如图所示：
  
  ![](docs/images/user-handbook_log1.png)
  
  日志管理提供了`Job`的运行日志相关信息，按项目组分组显示，一条Job日志的关键元素包含：
  
  * 执行状态：表示该Job执行结果；
  
  * 执行时间：表示调度器调度该Job的时间；
  
  * 执行完成时间：表示该Job执行完成的时间；
  
  * 调度信息：表示执行该Job的调度器实例；
  
  * 执行信息：该Job执行的具体信息
  
  并且已实现`Job`与所引用的`Task`的执行日志信息的关联，日志默认保存七天。
  
  * 标识1：点击下拉框，选定某一组名，可实现日志分组过滤；
  
  * 标识2：点击级联箭头，可显示出某个项目组的Job运行日志列表；
  
  * 标识3：点击标识3处过滤图标，可实现按Job_Key进行日志过滤；
  
  * 标识4：点击标识4处级联箭头，可现实该Job所引用的Task运行日志，实现Job与所引用Task运行日志的关联，如下图所示：
  
  ![](docs/images/user-handbook_log3.png)
  
  Task日志中关键元素包含：
  
  * 执行状态：表示该Task执行结果；
  
  * 执行时间：表示该Task执行时间；
  
  * 执行信息：表示该Task的具体执行器实例信息及出参
  
  * endTask：当某个Job所引用的Task均执行成功后，会执行系统自动追加的endTAsk，表示该Job执行完毕

