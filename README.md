netbeans-buildxml-joomla-components
===================================

A build file I wrote to help speed up the packaging, testing and deployment of my Joomla! components.

  WHAT IT DOES
  ____________
     
      * Zips your component into a nbproject/package/${name}.zip file
      * SFTPs your components files into the proper directories as long as remote.directory is set properly 
         (You do that in your project configuration when you specify Remote)
      * Copies the files to your local Joomla! installation for testing.    
      
       SHORT PROCESS (FYI)
       __________________
      * loads the nbproject/project.properties file
      * loads the private/private.properties file
      * loads the FTP connections file that you specify in the private.properies file
      ** NOTE: You can specify your ${ftp.connections} file directly here.
        
      
       INSTRUCTIONS
      ______________ 
      
      
       ### Set up SCP/SFTP
      
      1. In Netbeans 7.2.1 the RemoteConnections directory is at:
            ${netbeans.user}\\config\\Preferences\\org\\netbeans\\modules\\php\\project\\RemoteConnections
         So you would place the following line into your nbproject/private/private.properties file ():           
            ftp.connections=${netbeans.user}\\config\\Preferences\\org\\netbeans\\modules\\php\\project\\RemoteConnections
      
      2. In that directory find the file/connection you are using for your project and put your password on a new line as follows:
          
                 password=XXX123YYY ; where XXX123YYY is your password       
      
      ### Set up Name and Local Web Root Properties
      
      3. Open your nbproject/project.properties  file and add the name of your 
         components entry point, i.e. if you component is called 'com_dog' use 'dog' as follows:
            
            name=dog
      4. In the same file enter the web.root of your local testing installation, i.e.:
                
           C:\\xampp\\htdocs\\joomla_root\\  ; or what ever it is on linux or Mac OS is thats your flavor
      
         
