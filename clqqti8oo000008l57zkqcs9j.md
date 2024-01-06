---
title: "Adding Custom Commands like 'Clear Screen' In Irb"
seoTitle: "Adding Custom Commands like 'Clear Screen' In Irb"
seoDescription: "Adding Custom Commands like 'Clear Screen' In Irb, master irb ruby, add reload custom commands."
datePublished: Fri Dec 29 2023 15:57:47 GMT+0000 (Coordinated Universal Time)
cuid: clqqti8oo000008l57zkqcs9j
slug: adding-custom-commands-like-clear-screen-in-irb
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1703866435331/06d6d10b-e0e3-47c8-aa9f-97e992f9715c.png
tags: mvc, productivity, programming-blogs, ruby, development, rails, ruby-on-rails, developer, tips, coding, programming-tips, ruby-on-rails-developer, devsan, irb, rubydeveloper

---

#### Introduction:

"Hey, fellow Ruby enthusiasts! Want to sprinkle some magic into your Ruby Interactive Ruby Shell (IRB)? Let's explore custom commands that'll personalize your IRB sessions and make Ruby exploration more enchanting!"

**Q:** How can we make Ruby IRB more magical?

**A:** By using custom commands! These gems of code add colorful greetings and dynamic interactions, making your IRB experience more lively and engaging.

**Q:** Why are custom commands essential for IRB?

**A:** They transform your IRB environment into a personalized playground. Imagine colorful greetings and real-time interactions; that's what these commands bring to the table!

**Q:** How do we implement these magical commands?

**A:** Let's dive into the code and explore step by step.

---

#### Full Code:

```ruby
def colorize_text(text, color_code)
  "\e[#{color_code}m#{text}\e[0m"
end

def time_greeting(username)
  current_time = Time.now
  greeting = case current_time.hour
             when 0..11
               colorize_text("Good morning", 32) # 32 represents green color
             when 12..17
               colorize_text("Good afternoon", 33) # 33 represents yellow color
             else
               colorize_text("Good evening", 34) # 34 represents blue color
             end

  system_name_message = "Hey #{username}"
  puts "#{system_name_message}! #{greeting}! It's #{current_time.strftime('%I:%M %p')} Happy exploring the Ruby world!"
end

def r
  reload!
  system("clear")
  username = ENV['USER']
  time_greeting(username)
end
```

#### Explanation:

The code consists of custom functions (`colorize_text`, `time_greeting`, and `r`) designed to enhance your IRB experience by providing personalized greetings based on the time of day.

1. `colorize_text` function:
    
    * Adds color to text based on the provided color code.
        
2. `time_greeting` function:
    
    * Generates a personalized greeting based on the current time of day.
        
3. `r` function:
    
    * Reloads the IRB environment and delivers a personalized greeting using `time_greeting`.
        

---

#### Adding to `.irbrc` File:

You can directly add on .`irbrc` in in you home directory `"cd ~"`

Or

To use these commands in every IRB session, add them to your `.irbrc` file:

```bash
# Example command to add these functions to .irbrc file
echo -e "YOUR_CODE_HERE" >> ~/.irbrc
```

#### LinkedIn Description:

"Transform your Ruby IRB with custom greetings! Explore how these commands add a touch of magic to your coding sessions. Let's make your Ruby exploration more vibrant! #Ruby #IRB #CustomCommands"

#### Tags:

#Ruby #IRB #CustomCommands #RubyMagic #CodingTips