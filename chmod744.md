Chmod change attributes from a file/folder  
  
chmod 666 means that all users can read and write but cannot execute  
chmod 777 allows all actions for all users  
chmod 744 allows only owner to do all actions; group and other users are allowed only to read  
  
permission to:  owner      group      other       
                /¯¯¯\      /¯¯¯\      /¯¯¯\  
octal:            6          6          6  
binary:         1 1 0      1 1 0      1 1 0  
what to permit: r w x      r w x      r w x  
   
binary         - 1: enabled, 0: disabled  
   
what to permit - r: read, w: write, x: execute  
   
permission to  - owner: the user that create the file/folder  
                 group: the users from group that owner is member  
                 other: all other users  
