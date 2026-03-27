# Seatwork #2 - Getting to know CSS Position and z-index.
### This seatwork will ask you to implement the different CSS position on a given code.
### short link to this .md file is: https://bit.ly/4c61P9K
#### Resources (also found in Khub week 5)
- [4 Minute Youtube Video on CSS Position](https://www.youtube.com/watch?v=YEmdHbQBCSQ)
- [CSS Position Tutorial](https://roycan.github.io/CssPositioningZIndexLab/)

### Instructions: 
1. This is individual submission in khub, but you can work with a partner.  When you submit in khub please place both your names in the submission bin.
2. Guided Activity (30 minutes), please follow what is being required.  

    - Make a copy of this .md file to your Q4 repository and name it as **SectionLNseatwork2.md** example **9LiCruzSeatwork2.md**. Place it in your q4 repository vscode local computer. Committing frequently to your Github repository.  
    - Copy the code below and paste it inside a new file (name it as SectionLNseatwork2.html). Place this file in the same location where the .md file is saved. 
    - Change the content values of the meta tags to your names for author/s and the date today for revised.
    - Please do the following tasks that will ask you to reposition HTML elements then answer the guided question for each task on the .md file. Commit changes to the .md file and to the .html file as well.
    **- This seatwork is worth 20pts and should be submitted by the end of the period** The link to [KHub submission bin](https://khub.mc.pshs.edu.ph/mod/assign/view.php?id=15481).
      - Submit the links to your .md file and .html file.

```html
<!DOCTYPE html>
<html>
<head>
  <meta name="author" content="<your names>" />
  <meta name="revised" content="<date today>" />
  <style>
    body { font-family: Arial, sans-serif; }
    .header, .footer {
      background: lightblue;
      padding: 10px;
    }
    .footer {
       opacity: 0.5;
    }
    .sidebar {
      background: lightgreen;
      width: 150px;
      height: 200px;
    }
    .content {
      background: lightyellow;
      width: 300px;
      height: 200px;
    }    
  </style>
</head>
<body>
  <div class="header">Header</div>
  <div class="sidebar">Sidebar</div>
  <div class="content">Main Content</div>
  <div class="footer">Footer</div>
</body>
</html>
```
### Step 1 (Static vs Relative):

- Add in css ```position: relative; top: 20px; left: 20px;``` to .sidebar.

- Guided Question: What changed compared to the default static positioning? Try to give different values to top and left or you can change it to bottom, right.

.sidebar got moved 20 px to the right and 20 px down relative to its original position.




### Step 2 (Fixed):

- Add in css ```position: fixed; bottom: 0; width: 100%;``` to .footer.

- Guided Question: What happens when you scroll the page? Why does the footer behave differently from position relative?

The footer remains fixed on the bottom of the screen regardless of scrolling. I moves differently because the position is fixed, meaning it doesn't move along with the other objects.

### Step 3 (Absolute):

- Add in css ```position: absolute; top: 66px; left: 200px;``` to .content.

- Guided Question: What is the effect of position: absolute on an element? How is it different from fixed?

It got moved 200 px to the right and 66 px to the bottom relative to .sidebar. This is different from fixed since it still moves when you scroll down and it's also relative to the parent element.   

### Step 4 : (Absolute)

- Add in html ```<div class="notice">Notice!</div>``` and include the css below:

```css
.notice {
    position: absolute;
    top: 60px;
    left: 400px;
    background: orange;
    padding: 10px;
    z-index: 2;
}
```

- Give .content a z-index: 1.

- Guided Question: Why does the notice appear on top of the content? What happens if you swap the z‑index values?

.notice appears on top of Main Content because the z-index is 2, which means that it's in the higher layer compared to other elements. The higher the z-index, the higher the layer, and if you swap them, then .content would be the one at the very top of .notice.

- Challenge: 
    * What changes that you have to do on the code that will position .notice box on the top right corner of the .content box? Please write the code on paper as well (both html and css on the part of .notice and .content).

    You have to make `right: 0;` and `top: 0;`, and you have to insert `<div class="notice">Notice!</div>` inside `<div class="content">Main Content`


    ```  <div class="content">Main Content
    <div class="notice">Notice!</div>
  </div> 
  ```

  and 

  ```
      .content {
      background: lightyellow;
      width: 300px;
      height: 200px;
      z-index: 1;
      position: relative; top: 66px; left: 200px;
    }    

    .notice {
    position: absolute;
    top: 0px;
    right: 0px;
    background: orange;
    padding: 10px;
    z-index: 2;
    }
  ```





    * Try to change the position of .content to relative then to fixed. What do you observed each time?

    When the position is fixed, .content moves up and moves relative to the viewport.

    
    * What do you observe on about the effect of z-index on .notice and .content boxes?

    Since the z-index of .content is 2, it's automatically placed on top of .content since .content has a lower z-index.

3. Please answer the following reflection questions (15 minutes)

    a. Could you summarize the differences between the CSS position values (static, relative, absolute, fixed)? 

    * Static: The default position
    * Relative: relative to it's static position
    * Absolute: relative to the parent element
    * Fixed: Not able to move and relative to viewport.

    b. How does absolute positioning depend on its parent element?

    * Since the position is absolute, it becomes somewhat relative to it's parent element.

    c. How do you differentiate sticky from fixed (you can research on sticky)?

    * When scrolling, the sticky position makes the element become relative until you can't scroll anymore. Once this happens, the element goes back to being fixed.

    d. If you were designing a webpage for a school event, how might you use positioning to highlight important information? Please give concrete examples.

    * I would make important elements that need to be seen fixed so they would always show up on the screen, and I would also make the z-index high for these important things.

