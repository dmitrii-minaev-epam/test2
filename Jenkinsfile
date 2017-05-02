node {
    stage('\u2776 one') {
        echo ">>>>>>> BUILD_URL=${env.BUILD_URL}"
        def workspace = pwd()
        echo ">>>>>>> workspace=${workspace}"
        checkout scm
        f = new File('test.file')
        if (!f.exists()) {
            sh("touch test.file")
            sh("echo '>>>>>>>>>>file created'")
        } else {
            fail(">>>>>>>>file exists")
        }
    }
    stage('\u2777 two') {
        echo ">>>>>>> BUILD_URL=${env.BUILD_URL}"
        def workspace = pwd()
        echo ">>>>>>> workspace=${workspace}"
        sh("if [ -f test.file ]; then echo '>>>>>>>>>>touch ok'; else echo '>>>>>>>>>>touch failed'; fi")
        sh("rm test.file")
    }
}
