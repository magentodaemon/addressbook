node {
/*   def mvnHome
   def version 
   stage('Preparation') {
      git 'https://github.com/magentodaemon/addressbook.git'
      mvnHome = tool 'LOCAL_MAVEN'
	  version = '2.3.5' 
   }
   stage('Review')
   {
	sh "'${mvnHome}/bin/mvn' pmd:pmd"

   }
   stage('Test')
   {
	sh "'${mvnHome}/bin/mvn' test"

   }	

   stage('Build') {
   //     withMaven(
   //     maven: 'LOCAL_MAVEN', // Maven installation declared in the Jenkins "Global Tool Configuration"
   //     mavenSettingsConfig: 'settings.xml', // Maven settings.xml file defined with the Jenkins Config File Provider Plugin
   //     mavenLocalRepo: 'd:/repos') {

      if (isUnix()) {
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
      } else {
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
      }
  //  } // withMaven will discover the generated Maven artifacts, JUnit reports and FindBugs reports
    

   }
   stage('Results') {
   }
   stage('Publish') {
     //nexusPublisher nexusInstanceId: 'NEXUS', nexusRepositoryId: 'releases', packages: [[$class: 'MavenPackage', mavenAssetList: [[classifier: '', extension: '', filePath: 'addressbook_main/target/addressbook.war']], mavenCoordinate: [artifactId: 'addressbook_main', groupId: 'com.edurekademo.tutorial', packaging: 'war', version: '2.3.5']]]
        if (isUnix()) {
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore deploy"
      } else {
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore deploy/)
      }
   } */
   stage("MergewithQa")
   {
      sh "'mkdir' /tmp/uploadtoqarelease"
      
      sh "'cd' /tmp/uploadtoqarelease"	
      sh "'git' clone git@github.com:magentodaemon/addressbook.git"
      sh "'cd' addressbook"

      sh "'git' checkout develop"	
      sh "'git' pull origin develop"
      sh "'git' checkout qarelease"
      sh "'git' pull origin qarelease"	      
      sh "'git' merge develop"
      sh "'git' add *"
      sh "'git commit -m 'new file changes'"
      sh "'git' push origin qarelease"			
      sh "'cd' /tmp"
      sh "'rm -rf' uploadtoqarelease"	 	
   }	
} 
