# utl-insert-html-text-into-an-existing-html-document
Inset html text into an existing html document  
    Inset html text into an existing html document                                                          
                                                                                                            
    github                                                                                                  
    https://tinyurl.com/y8953pc2                                                                            
    https://github.com/rogerjdeangelis/utl-insert-html-text-into-an-existing-html-document                  
                                                                                                            
    Stackoverflow                                                                                           
    https://tinyurl.com/yd4k28gy                                                                            
    https://stackoverflow.com/questions/62247993/merging-two-html-strings-into-one-using-python             
                                                                                                            
    This solution uses a placeholder                                                                        
                                                                                                            
    http://www.example.com                                                                                  
                                                                                                            
    "This domain is for use in illustrative examples in documents.                                          
    You may use this domain in literature without prior coordination or asking for permission."             
    *_                   _                                                                                  
    (_)_ __  _ __  _   _| |_                                                                                
    | | '_ \| '_ \| | | | __|                                                                               
    | | | | | |_) | |_| | |_                                                                                
    |_|_| |_| .__/ \__,_|\__|                                                                               
            |_|                                                                                             
    ;                                                                                                       
                                                                                                            
    %let fromsas=                                                                                           
    <html>                                                                                                  
     <body>                                                                                                 
       <p>my paragraph</p>                                                                                  
     </body>                                                                                                
    </html>                                                                                                 
    ;                                                                                                       
                                                                                                            
    %put &=fromsas;                                                                                         
                                                                                                            
    FROMSAS = <html><body><p>my paragraph</p><a href="http://www.example.com"></a></body></html>            
                                                                                                            
    *            _               _                                                                          
      ___  _   _| |_ _ __  _   _| |_                                                                        
     / _ \| | | | __| '_ \| | | | __|                                                                       
    | (_) | |_| | |_| |_) | |_| | |_                                                                        
     \___/ \__,_|\__| .__/ \__,_|\__|                                                                       
                    |_|                                                                                     
    ;                                                                                                       
                                              | RULES                                                       
    <HTML>                                    | =====                                                       
      <body>                                  |                                                             
      <p>my paragraph</p>                     |                                                             
                                                                                                            
      <a href="http://www.example.com"></a>   | Add this line to the html code above                        
                                                                                                            
      </body>                                 |                                                             
    </html>                                   |                                                             
                                                                                                            
    *                                                                                                       
     _ __  _ __ ___   ___ ___  ___ ___                                                                      
    | '_ \| '__/ _ \ / __/ _ \/ __/ __|                                                                     
    | |_) | | | (_) | (_|  __/\__ \__ \                                                                     
    | .__/|_|  \___/ \___\___||___/___/                                                                     
    |_|                                                                                                     
    ;                                                                                                       
                                                                                                            
    %symdel fompy / nowarn;                                                                                 
                                                                                                            
    %utl_submit_py64_38(resolve('                                                                           
    import bs4;                                                                                             
    import io;                                                                                              
    import pyperclip;                                                                                       
    from bs4 import BeautifulSoup;                                                                          
    soup = BeautifulSoup("&fromsas");                                                                       
    body = soup.find("body");                                                                               
    new_tag = soup.new_tag("a", href="http://www.example.com");                                             
    body.append(new_tag);                                                                                   
    output = io.StringIO();                                                                                 
    print(soup,file=output,end="");                                                                         
    output = output.getvalue();                                                                             
    pyperclip.copy(output);                                                                                 
    output.close();                                                                                         
    '),return=fromPy);                                                                                      
                                                                                                            
    %put &=frompy;                                                                                          
                                                                                                            
