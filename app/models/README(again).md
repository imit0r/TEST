PS C:\Users\LEGION\Desktop\TEST> rails c
Loading development environment (Rails 7.0.4.3)
irb(main):001:0> A



irb(main):001:0> Article.all
  Article Load (0.2ms)  SELECT "articles".* FROM "articles"
=>                                                                 
[#<Article:0x00000201cafd8d10                                      
  id: 1,                                                           
  title: "first article",                                          
  description: "description of first article",                     
  created_at: Tue, 28 Mar 2023 08:02:04.279803000 UTC +00:00,      
  updated_at: Tue, 28 Mar 2023 08:02:04.279803000 UTC +00:00>,     
 #<Article:0x00000201cad0ce60                                      
  id: 2,                                                           
  title: "second article",                                         
  description: "description of second article",
  created_at: Tue, 28 Mar 2023 08:05:37.559793000 UTC +00:00,
  updated_at: Tue, 28 Mar 2023 08:05:37.559793000 UTC +00:00>,
 #<Article:0x00000201cad0cdc0
  id: 3,
  title: "third article",
  description: "description of third article",
  created_at: Tue, 28 Mar 2023 08:07:37.768213000 UTC +00:00,
  updated_at: Tue, 28 Mar 2023 08:07:37.768213000 UTC +00:00>]
irb(main):002:0> A
irb(main):002:0> Article.find(2)
  Article Load (0.2ms)  SELECT "articles".* FROM "articles" WHERE "articles"."id" = ? LIMIT ?  [["id", 2], ["LIMIT", 1]]            
=>                                                    
#<Article:0x00000201cad09080                          
 id: 2,                                               
 title: "second article",                             
 description: "description of second article",        
 created_at: Tue, 28 Mar 2023 08:05:37.559793000 UTC +00:00,
 updated_at: Tue, 28 Mar 2023 08:05:37.559793000 UTC +00:00>
irb(main):003:0> A
                                                      
irb(main):003:0> Article.first
  Article Load (0.3ms)  SELECT "articles".* FROM "articles" ORDER BY "articles"."id" ASC LIMIT ?  [["LIMIT", 1]]
=> 
#<Article:0x00000201cabca020
 id: 1,
 title: "first article",
 description: "description of first article",
 created_at: Tue, 28 Mar 2023 08:02:04.279803000 UTC +00:00,
 updated_at: Tue, 28 Mar 2023 08:02:04.279803000 UTC +00:00>
irb(main):004:0> article = A



irb(main):004:0> article = Article.find(3)
  Article Load (0.2ms)  SELECT "articles".* FROM "articles" WHERE "articles"."id" = ? LIMIT ?  [["id", 3], ["LIMIT", 1]]
=> 
#<Article:0x00000201cad0cf00
...
irb(main):005:0> article
=>
#<Article:0x00000201cad0cf00
 id: 3,
 title: "third article",
 description: "description of third article",
 created_at: Tue, 28 Mar 2023 08:07:37.768213000 UTC +00:00,
 updated_at: Tue, 28 Mar 2023 08:07:37.768213000 UTC +00:00>
irb(main):006:0> A


irb(main):006:0> articles = Article.all
  Article Load (0.2ms)  SELECT "articles".* FROM "articles"
=>            
[#<Article:0x00000201cad0c000           
...           
irb(main):007:0> articles
=>
[#<Article:0x00000201cad0c000           
  id: 1,           
  title: "first article",           
  description: "description of first article",           
  created_at: Tue, 28 Mar 2023 08:02:04.279803000 UTC +00:00,           
  updated_at: Tue, 28 Mar 2023 08:02:04.279803000 UTC +00:00>,
 #<Article:0x00000201cad0bf60
  id: 2,
  title: "second article",
  description: "description of second article",
  created_at: Tue, 28 Mar 2023 08:05:37.559793000 UTC +00:00,
  updated_at: Tue, 28 Mar 2023 08:05:37.559793000 UTC +00:00>,
 #<Article:0x00000201cad0bec0
  id: 3,
  title: "third article",
  description: "description of third article",
  created_at: Tue, 28 Mar 2023 08:07:37.768213000 UTC +00:00,
  updated_at: Tue, 28 Mar 2023 08:07:37.768213000 UTC +00:00>]
irb(main):008:0* article.
                 article   
                 articles  

irb(main):008:0> article.title
=> "third article"
irb(main):009:0* article.
                 article                                  
                 articles                                 
                                                          
irb(main):009:0> article.description
=> "description of third article"
irb(main):010:0> A



irb(main):010:0> article.description = "edited - description of turd article"
=> "edited - description of turd article"
irb(main):011:0> article
=>
#<Article:0x00000201cad0cf00
 id: 3,
 title: "third article",
 description: "edited - description of turd article",
 created_at: Tue, 28 Mar 2023 08:07:37.768213000 UTC +00:00,
 updated_at: Tue, 28 Mar 2023 08:07:37.768213000 UTC +00:00>
irb(main):012:0> A



irb(main):012:0> Article.find(3)
  Article Load (0.1ms)  SELECT "articles".* FROM "articles" WHERE "articles"."id" = ? LIMIT ?  [["id", 3], ["LIMIT", 1]]            
=>                                                    
#<Article:0x00000201cad488e8                          
 id: 3,                                               
 title: "third article",                              
 description: "description of third article",         
 created_at: Tue, 28 Mar 2023 08:07:37.768213000 UTC +00:00,
 updated_at: Tue, 28 Mar 2023 08:07:37.768213000 UTC +00:00>
irb(main):013:0> A
                                                      
irb(main):013:0> Article.save
C:/Ruby32-x64/lib/ruby/gems/3.2.0/gems/activerecord-7.0.4.3/lib/active_record/dynamic_matchers.rb:22:in `method_missing': undefined method `save' for Article:Class (NoMethodError)
irb(main):014:0* article.
                 article   
                 articles  

irb(main):014:0> article.save
  TRANSACTION (0.1ms)  begin transaction
  Article Update (1.5ms)  UPDATE "articles" SET "description" = ?, "updated_at" = ? WHERE "articles"."id" = ?  [["description", "edited - description of turd article"], ["updated_at", "2023-03-31 13:37:35.579188"], ["id", 3]]
  TRANSACTION (4.9ms)  commit transaction
=> true
irb(main):015:0> A



irb(main):015:0> article = Article.first
  Article Load (0.1ms)  SELECT "articles".* FROM "articles" ORDER BY "articles"."id" ASC LIMIT ?  [["LIMIT", 1]]       
=> 
#<Article:0x00000201c93feec8
...
irb(main):016:0* article.
                 article   
                 articles  

irb(main):016:0> article.destroy
  TRANSACTION (0.0ms)  begin transaction
  Article Destroy (1.6ms)  DELETE FROM "articles" WHERE "articles"."id" = ?  [["id", 1]]
  TRANSACTION (3.3ms)  commit transaction                
=>                                                       
#<Article:0x00000201c93feec8                             
 id: 1,                                                  
 title: "first article",
 description: "description of first article",
 created_at: Tue, 28 Mar 2023 08:02:04.279803000 UTC +00:00,
 updated_at: Tue, 28 Mar 2023 08:02:04.279803000 UTC +00:00>
irb(main):017:0> A
irb(main):017:0> Article.all
  Article Load (0.1ms)  SELECT "articles".* FROM "articles"
=>                                                                 
[#<Article:0x00000201c941a3d0                                      
  id: 2,                                                           
  title: "second article",                                         
  description: "description of second article",                    
  created_at: Tue, 28 Mar 2023 08:05:37.559793000 UTC +00:00,      
  updated_at: Tue, 28 Mar 2023 08:05:37.559793000 UTC +00:00>,     
 #<Article:0x00000201c9419c50                                      
  id: 3,                                                           
  title: "third article",                                          
  description: "edited - description of turd article",
  created_at: Tue, 28 Mar 2023 08:07:37.768213000 UTC +00:00,
  updated_at: Fri, 31 Mar 2023 13:37:35.579188000 UTC +00:00>]
irb(main):018:0> A
irb(main):018:0> reload!
Reloading...
=> true                                   
irb(main):019:0> article = A
                                          
                                          
                                          
irb(main):019:0> article = Article.new
=>
#<Article:0x00000201ca9e61f0
...
irb(main):020:0* article.
                 article   
                 articles  

irb(main):020:0> article.save
  TRANSACTION (0.1ms)  begin transaction
  Article Create (1.2ms)  INSERT INTO "articles" ("title", "description", "created_at", "updated_at") VALUES (?, ?, ?, ?)  [["title", nil], ["description", nil], ["created_at", "2023-03-31 13:50:46.461541"], ["updated_at", "2023-03-31 13:50:46.461541"]]
  TRANSACTION (4.7ms)  commit transaction
=> true
irb(main):021:0> r



irb(main):021:0> reload!
Reloading...
=> true                                   
irb(main):022:0> article = A
                                          
                                          
                                          
irb(main):022:0> article = Article.new
=>
#<Article:0x00000201cb0b4568
...
irb(main):023:0> A



irb(main):023:0> article.save
=> false
irb(main):024:0* article.
                 article   
                 articles  

irb(main):024:0> article.errors
=> #<ActiveModel::Errors [#<ActiveModel::Error attribute=title, type=blank, options={}>]>   
irb(main):025:0* article.
                 article   
                 articles  

irb(main):025:0> article.errors.full_messages
=> ["Title can't be blank"]
irb(main):026:0> r



irb(main):026:0> reload!
Reloading...
=> true                                   
irb(main):027:0> article = A
                                          
                                          
                                          
irb(main):027:0> article = Article.new
=>
#<Article:0x00000201cb036960
...
irb(main):028:0* article.
                 article   
                 articles  

irb(main):028:0> article.save
=> false
irb(main):029:0* article.
                 article   
                 articles  

irb(main):029:0> article.errors.full_messages
=> ["Title can't be blank", "Description can't be blank"]
irb(main):030:0* article.
                 article   
                 articles  
                           
irb(main):030:0> article.title = "test article"
=> "test article"
irb(main):031:0* article.
                 article                                  
                 articles                                 
                                                          
irb(main):031:0> article.save
=> false
irb(main):032:0* article.
                 article   
                 articles  

irb(main):032:0> article.errors.full_messages
=> ["Description can't be blank"]
irb(main):033:0* article.
                 article   
                 articles  

irb(main):033:0> article.description
=> nil
irb(main):034:0* article.
                 article   
                 articles  
                                                    
irb(main):034:0> article.description



irb(main):034:0> article.description = "Test description"
=> "Test description"
irb(main):035:0* article.
                 article                                           
                 articles                                          
irb(main):035:0> article.save
  TRANSACTION (0.1ms)  begin transaction
  Article Create (0.7ms)  INSERT INTO "articles" ("title", "description", "created_at", "updated_at") VALUES (?, ?, ?, ?)  [["title", "test article"], ["description", "Test description"], ["created_at", "2023-03-31 13:57:00.418891"], ["updated_at", "2023-03-31 13:57:00.418891"]]                                                        
  TRANSACTION (4.9ms)  commit transaction                          
=> true                                                            
irb(main):036:0> article = A
                                                                   
                                                                   
irb(main):036:0> article = Article.new(title: 'a', description: 'b')
=>
#<Article:0x00000201cbe58ac0                                       
...                                                                
irb(main):037:0* article.
                 article                                           
                 articles                                          
irb(main):037:0> article.save
  TRANSACTION (0.1ms)  begin transaction
  Article Create (1.8ms)  INSERT INTO "articles" ("title", "description", "created_at", "updated_at") VALUES (?, ?, ?, ?)  [["title", "a"], ["description", "b"], ["created_at", "2023-03-31 13:58:29.312588"], ["updated_at", "2023-03-31 13:58:29.312588"]]               
  TRANSACTION (5.9ms)  commit transaction                          
=> true                                                            
irb(main):038:0> r
                                                                   
                                                                   
irb(main):038:0> reload!Reloading...
=> true                                   
irb(main):039:0> A
                                          
                                          
irb(main):039:0> article = Article.new(title: 'a', description: 'b')
=>
#<Article:0x00000201cb074f80                                       
...                                                                
irb(main):040:0* article.
                 article                                           
                 articles                                          
irb(main):040:0> article.save
=> false
irb(main):041:0* article.
                 article                                           
                 articles                                          
irb(main):041:0> article.errors.full_message
C:/Ruby32-x64/lib/ruby/gems/3.2.0/gems/activemodel-7.0.4.3/lib/active_model/errors.rb:426:in `full_message': wrong number of arguments (given 0, expected 2) (ArgumentError)                             
irb(main):042:0> article.errors.full_messages
=>
["Title is too short (minimum is 6 characters)",                   
 "Description is too short (minimum is 10 characters)"]            
irb(main):043:0* article.
                 article                                           
                 articles                                          
irb(main):043:0> article.title = "This should spice things up"     => "This should spice things up"
irb(main):044:0* article.
                 article                                           
                 articles                                          
irb(main):044:0> article.description = "This is a spicy description"
=> "This is a spicy description"
irb(main):045:0* article.
                 article                                           
                 articles                                          
irb(main):045:0> article.save
  TRANSACTION (0.1ms)  begin transaction
  Article Create (1.5ms)  INSERT INTO "articles" ("title", "description", "created_at", "updated_at") VALUES (?, ?, ?, ?)  [["title", "This should spice things up"], ["description", "This is a spicy description"], ["created_at", "2023-03-31 14:03:27.693247"], ["updated_at", "2023-03-31 14:03:27.693247"]]                              
  TRANSACTION (4.3ms)  commit transaction                          
=> true                                                            
irb(main):046:0>