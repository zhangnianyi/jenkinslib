#!groovy
@Library('jenkinslib') _ 
 def tools = new org.devops.tools()
  pipeline{
     agent{
         node{  label "master"

         }
     }
     parameters { string(name: 'DEPLOY_ENV', defaultValue: 'staging', description: '') }
     options{
         timestamps()
         skipDefaultCheckout()
         disableConcurrentBuilds()
         timeout(time:1,unit: 'HOURS')

     }
     stages{
         stage("Getcode"){
             steps{
                 when {
               
                    environment name: 'test', value: 'abcd'
                }
                 input id: 'Test-input', message: '我们是否要继续呢？', ok: '是', parameters: [choice(choices: ['a', 'b'], description: '', name: 'test1')], submitter: 'zhangnianyi,admin'
                 timeout(time:5,unit:"MINUTES"){
                 script{
                     println("获取代码")
                     println("${test}")
                     mvnhome =tool "m2"
                     println("${mvnhome}")
                     sh "${mvnhome}/bin/mvn --version"
                     tools.printMesI("zhangchao is my father")
                 }
             }
         }
 }
 }
 }
