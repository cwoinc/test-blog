# az-project定时任务时间表

## mws-finances
| 类名 | 方法名 | 执行时间 | 备注信息 |
| ------ | ------ | ------ | ------ | 
| FeEventsTask | startFetchFeEventsTask | 启动后执行，然后每隔5秒一次 | 根据14天账期获取event数据，如果没有需要拉取的数据，则休眠1小时。 |
| FeGroupsTask |  startFetchFeGroupsTask| 启动后执行，然后每隔5分钟执行一次 | 获取14天账期数据，如果已经获取完历史数据，则每3小时更新一次数据。 |
| FeServiceTask | getShopNameTask | 启动后执行，然后每隔24小时执行一次 | 获取店铺名称 |
|  | checkFeServiceIsNormal | 启动后执行，然后每隔2小时执行一次 | 检查亚马逊服务是否正常。 |

## mws-reports
| 类名 | 方法名 | 执行时间 | 备注信息 |
| ------ | ------ | ------ | ------ | 
| FulfillmentReportTask | startRequestReportTaskByDay | 每天上午9:30:20执行一次 | 获取亚马逊长期库存报告。 |
|  | startRequestReportTaskByMonth | 每月1号20:20:20执行一次 | 获取节点树报告。 |
|  | startRequestDailyInventoryHistoryReportTask | 启动后执行，然后每隔5分钟执行一次 | 获取亚马逊每日历史库存、亚马逊收货报告。全部拉取完后，则休眠2小时，后面就是每天拉取一次了。 |
|  | startRequestMonthInventoryHistoryReportTask | 启动后执行，然后每隔5分钟执行一次 | 获取亚马逊每月历史库存报告。全部拉取完后，则休眠24小时，后面就是每月拉取一次。 |
|ReportTask|requestReportTask|每天00:24执行一次|发送需要拉取的报告类型|
|  |update|每5分钟执行一次|从亚马逊上更新报告的状态|
|  |getReport|每5分钟执行一次|从亚马逊上拉取报告|
|  |insertDataFromReport|每5分钟执行一次|将拉取的报告存入数据库中|
| TaxReportTask | requestTaxReportTask | 每月1号22:15 |
| | getTaxVatReportTask | 每月1号22:30 | 需要后台请求 |
| AdsReportTask | requestDailyAdsReport | 每日20:15 |
| | requestWeeklyAdsReport | 每周一18:30 |
| | requestMonthlyAdsReport | 每月1号21:10 |


## mws-inventory
| 类名 | 方法名 | 执行时间 | 备注信息 |
| ------ | ------ | ------ | ------ | 
| InventoryTask | task | 一个小时执行一次 | 更新mws库存 |

## mws-outbound
| 类名 | 方法名 | 执行时间 | 备注信息 |
| ------ | ------ | ------ | ------ | 
| OutboundTask | task | 每天23:24执行 | 更新出库信息 |

## mws-product
| 类名 | 方法名 | 执行时间 | 备注信息 |
| ------ | ------ | ------ | ------ | 
| ProductTask | task | 每天22:24执行 | 更新商品的信息 |

## mws-inbound
| 类名 | 方法名 | 执行时间 | 备注信息 |
| ------ | ------ | ------ | ------ | 
| InboundTask | getInboundTask | 每天10:10 | |

## mws-orders
| 类名 | 方法名 | 执行时间 | 备注信息 |
| ------ | ------ | ------ | ------ | 
| OrdersTask | getServiceStatusTask | 每30min一次 |
| OrdersTask | startOrderTask | 每5min一次|
| OrdersTask | getOrderItemTask | 每30s一次|

## mws-recommendation
| 类名 | 方法名 | 执行时间 | 备注信息 |
| ------ | ------ | ------ | ------ | 
| RecommendationTask | getRecommendationTask | 每天19:15 |

## mws-subscriptions
| 类名 | 方法名 | 执行时间 | 备注信息 |
| ------ | ------ | ------ | ------ | 
| SubscriptionsTask | startTask | 每5min进行一次轮询 |





## ads-campaign
| 类名 | 方法名 | 执行时间 | 备注信息 |
| ------ | ------ | ------ | ------ | 
| CampaignExtendedTask | getShopNameTask | 启动后执行，然后每隔24小时执行一次 | 获取店铺信息 |
|  | startFetchCampaignExtendedTask | 每小时的10分和40分的时候执行 | 获取广告campaign数据，并根据策略调整超出预算的预算信息 |


## ads-keyword
| 类名 | 方法名 | 执行时间 | 备注信息 |
| ------ | ------ | ------ | ------ | 
| KeywordTask | startTask | 每天21:15 | |

## ads-product
| 类名 | 方法名 | 执行时间 | 备注信息 |
| ------ | ------ | ------ | ------ | 
| ProductTask | startTask | 每天23:15 | |

## ads-group
| 类名 | 方法名 | 执行时间 | 备注信息 |
| ------ | ------ | ------ | ------ | 
| GroupTask | startTask | 每天21:24 | |

## ads-reporting
| 类名 | 方法名 | 执行时间 | 备注信息 |
| ------ | ------ | ------ | ------ | 
| reportingTask | task | 每天16:33 | |
## ads-snapshot
| 类名 | 方法名 | 执行时间 | 备注信息 |
| ------ | ------ | ------ | ------ | 
| SnapshotTask | task | 每天21:24 | |

## az-shopify
| 类名 | 方法名 | 执行时间 | 备注信息 |
| ------ | ------ | ------ | ------ | 
| ProductTask | task | 每天4:24 和16:24执行一次 | 更新保存商品的信息 |
|  | updateInventroyFromAmzon | 一个小时进行一次 | 由inventory进行事件驱动 |