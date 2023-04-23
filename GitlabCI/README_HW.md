    stages:
        build
        test
    
    Building:
        stage: build
        script:
            - mkdir /build
            - touch /build/info.txt
        tags: netology
    
    Testing:
        stage: test
        script: ls /build
        tags: netology