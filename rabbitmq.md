#### pda/pheanstalk

php client for beanstalkd queue





~~~
//connect queue client
$p=new Pheanstalk('localhost',11300);
dump($p)
~~~

![image-20240406173500777](D:\github_document\StudyFiles\rabbitmq.assets\image-20240406173500777.png)



#### 订单取消

~~~

//消费者需要订阅channel，才可以进行消费
$data=[];
//使用channel发送数据，没有则会创建
$id=$p->useTube('trade')->put(json_encode($data));


//监听trade channel 获取消费,default是默认存在的channel
$job=$p->watch('trade')->ingore('default')->reserve();
dump(json_decode($job->getData()));

~~~



#### 支付通知



#### 短信邮件通知



