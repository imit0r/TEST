PS C:\Users\LEGION\Desktop\TEST> pwd

Path
----
C:\Users\LEGION\Desktop\TEST


PS C:\Users\LEGION\Desktop\TEST> rails generate migration add_timestamps_to_articles
      invoke  active_record
      create    db/migrate/20230328074945_add_timestamps_to_articles.rb
PS C:\Users\LEGION\Desktop\TEST> rails db:migrate
== 20230328074945 AddTimestampsToArticles: migrating ==========================
-- add_column(:articles, :created_at, :datetime)
   -> 0.0024s
-- add_column(:updated_at, :datetime)
rails aborted!
StandardError: An error has occurred, this and all later migrations canceled:

wrong number of arguments (given 2, expected 3)
C:/Users/LEGION/Desktop/TEST/db/migrate/20230328074945_add_timestamps_to_articles.rb:4:in `change'

Caused by:
ArgumentError: wrong number of arguments (given 2, expected 3)
C:/Users/LEGION/Desktop/TEST/db/migrate/20230328074945_add_timestamps_to_articles.rb:4:in `change'
Tasks: TOP => db:migrate
(See full trace by running task with --trace)
PS C:\Users\LEGION\Desktop\TEST> rails db:migrate
== 20230328074945 AddTimestampsToArticles: migrating ==========================
-- add_column(:articles, :created_at, :datetime)
   -> 0.0021s
-- add_column(:articles, :updated_at, :datetime)
   -> 0.0006s
== 20230328074945 AddTimestampsToArticles: migrated (0.0045s) =================

PS C:\Users\LEGION\Desktop\TEST> pwd

Path
----
C:\Users\LEGION\Desktop\TEST


PS C:\Users\LEGION\Desktop\TEST> rails c
Loading development environment (Rails 7.0.4.3)
irb(main):001:0> A
irb(main):001:0> Art
(irb):1:in `<main>': uninitialized constant Art (NameError)

Art
^^^
Did you mean?  Arel
irb(main):002:0> A



irb(main):002:0> Article.all
  Article Load (0.1ms)  SELECT "articles".* FROM "articles"
=> []                                                              
irb(main):003:0> A
                                                                   
                                                                   
                                                                   
irb(main):003:0> Article.create(title: "first article", description: "description of first article")
  TRANSACTION (0.0ms)  begin transaction
  Article Create (1.3ms)  INSERT INTO "articles" ("title", "description", "created_at", "updated_at") VALUES (?, ?, ?, ?)  [["title", "first article"], ["description", "description of first article"], ["created_at", "2023-03-28 08:02:04.279803"], ["updated_at", "2023-03-28 08:02:04.279803"]]                                                                            
  TRANSACTION (4.8ms)  commit transaction                                                   
=>                                                                                          
#<Article:0x000001f0e3f3f590                                                                
 id: 1,
 title: "first article",
 description: "description of first article",
 created_at: Tue, 28 Mar 2023 08:02:04.279803000 UTC +00:00,
 updated_at: Tue, 28 Mar 2023 08:02:04.279803000 UTC +00:00>
irb(main):004:0> A
irb(main):004:0> Article.all
  Article Load (0.2ms)  SELECT "articles".* FROM "articles"
=>                                                                 
[#<Article:0x000001f0e45ee760                                      
  id: 1,                                                           
  title: "first article",                                          
  description: "description of first article",                     
  created_at: Tue, 28 Mar 2023 08:02:04.279803000 UTC +00:00,      
  updated_at: Tue, 28 Mar 2023 08:02:04.279803000 UTC +00:00>]     
irb(main):005:0> A
                                                                   
                                                                   
irb(main):005:0> article = Article.new
=>
#<Article:0x000001f0e45ebe20
...
irb(main):006:0* article.
                           


irb(main):006:0> article.title = "second article"
=> "second article"
irb(main):007:0* article.
                                                          
                                                          
                                                          
irb(main):007:0> article.description = "description of second article"
=> "description of second article"
irb(main):008:0> article
=>
#<Article:0x000001f0e45ebe20
 id: nil,
 title: "second article",
 description: "description of second article",
 created_at: nil,          
 updated_at: nil>          
irb(main):009:0* article.
                           


irb(main):009:0> article.save
  TRANSACTION (0.0ms)  begin transaction
  Article Create (0.7ms)  INSERT INTO "articles" ("title", "description", "created_at", "updated_at") VALUES (?, ?, ?, ?)  [["title", "second article"], ["description", "description of second article"], ["created_at", "2023-03-28 08:05:37.559793"], ["updated_at", "2023-03-28 08:05:37.559793"]]
  TRANSACTION (4.9ms)  commit transaction
=> true
irb(main):010:0> A



irb(main):010:0> Article.all
  Article Load (0.1ms)  SELECT "articles".* FROM "articles"
=>                                                                 
[#<Article:0x000001f0e45edd60                                      
  id: 1,                                                           
  title: "first article",                                          
  description: "description of first article",                     
  created_at: Tue, 28 Mar 2023 08:02:04.279803000 UTC +00:00,      
  updated_at: Tue, 28 Mar 2023 08:02:04.279803000 UTC +00:00>,     
 #<Article:0x000001f0e45edc20                                      
  id: 2,                                                           
  title: "second article",                                         
  description: "description of second article",
  created_at: Tue, 28 Mar 2023 08:05:37.559793000 UTC +00:00,
  updated_at: Tue, 28 Mar 2023 08:05:37.559793000 UTC +00:00>]
irb(main):011:0> article
=>
#<Article:0x000001f0e45ebe20
 id: 2,
 title: "second article",
 description: "description of second article",
 created_at: Tue, 28 Mar 2023 08:05:37.559793000 UTC +00:00,
 updated_at: Tue, 28 Mar 2023 08:05:37.559793000 UTC +00:00>
irb(main):012:0> article = A
                           


irb(main):012:1" article = Article.new(title: "third article", description: "description of irb(main):012:0> article = Article.new(title: "third article", description: "description of third article")
=>
#<Article:0x000001f0e44ec448
...
irb(main):013:0* article.
                           


irb(main):013:0> article.save
  TRANSACTION (0.1ms)  begin transaction
  Article Create (1.5ms)  INSERT INTO "articles" ("title", "description", "created_at", "updated_at") VALUES (?, ?, ?, ?)  [["title", "third article"], ["description", "description of third article"], ["created_at", "2023-03-28 08:07:37.768213"], ["updated_at", "2023-03-28 08:07:37.768213"]]
  TRANSACTION (3.1ms)  commit transaction
=> true
irb(main):014:0> A



irb(main):014:0> Article.all
  Article Load (0.1ms)  SELECT "articles".* FROM "articles"
=>                                                                 
[#<Article:0x000001f0e44ed208                                      
  id: 1,                                                           
  title: "first article",                                          
  description: "description of first article",                     
  created_at: Tue, 28 Mar 2023 08:02:04.279803000 UTC +00:00,      
  updated_at: Tue, 28 Mar 2023 08:02:04.279803000 UTC +00:00>,     
 #<Article:0x000001f0e44ed0c8                                      
  id: 2,                                                           
  title: "second article",                                                                  
  description: "description of second article",
  created_at: Tue, 28 Mar 2023 08:05:37.559793000 UTC +00:00,
  updated_at: Tue, 28 Mar 2023 08:05:37.559793000 UTC +00:00>,
 #<Article:0x000001f0e44ecf88
  id: 3,
  title: "third article",
  description: "description of third article",
  created_at: Tue, 28 Mar 2023 08:07:37.768213000 UTC +00:00,
  updated_at: Tue, 28 Mar 2023 08:07:37.768213000 UTC +00:00>]
irb(main):015:0>