pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git url: 'git@github.com:your-org/your-repo.git', branch: 'main'
            }
        }

        stage('Run Audit Script') {
            steps {
                sh 'chmod +x audit_and_prepare_branch_actions.sh'
                sh './audit_and_prepare_branch_actions.sh 2025-01-01'
            }
        }

        stage('Archive Report') {
            steps {
                archiveArtifacts artifacts: 'old_branches_report_*.csv', fingerprint: true
            }
        }
    }
}

