    - name: Home Work Server
      hosts: all  # есть место только для 1 хоста
      become: yes
    
      tasks:
        -  name: Building
          ansible.builtin.file:
          path: /home/build/info.txt
          state: file
          mode: '0755'
          tags: netology
        - name: Testing
            - shell: ls /home/build
              tags: netology