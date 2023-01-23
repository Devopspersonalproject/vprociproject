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
        NEXUS_VERSION = "nexus3"
        NEXUS_PROTOCOL = "http"
        NEXUSPORT = "8081"
        NEXUS_URL = "172.31.26.24"
        NEXUS_REPOSITORY = "vprofile-release"
	    NEXUS_REPOGRP_ID    = "vprofile-maven-group"
        CENTRAL_REPOT = "vpro-maven-central"
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

    
