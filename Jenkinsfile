pipeline {
    
	agent any
	
	tools {
        maven "MAVEN3"
        jdk "OracleJDK8"
    }

    environment {
        SNAP_REPO = "vprofile-snapshot"
        NEXUS_USER = "admin"
        NEXUS_PASS = "Bodymender04@"
        RELEASE_REPO = "vprofile-release"
        CENTRAL_REPO = "vpro-maven-central"
        NEXUS_VERSION = "nexus3"
        NEXUSPORT = "8081"
        NEXUS_URL = "172.31.26.24"
	    NEXUS_REPOGRP_ID    = "vprofile-maven-group"
        NEXUS_CREDENTIAL_ID = "nexuslogin"
        
    
  
    }
	
    stages {
        
        stage('Build'){
            steps {
                sh 'mvn -s settings.xml -DskipTests install'
            }
            post {
                success {
                    echo 'Now Archiving.'
                    archiveArtifacts artifacts: '**/*.war'
                }
            }
        }
    }

    
