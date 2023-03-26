# react-notes




#lecture 4

Que.1 parcel delete console.log or not?
ans:- no, parcel does not remove. when we r using parcel and babel it does not directly remove.we can remove console log automatically.  we have to configure project to remove console log.

when we can't find console log to delete ,here is plugin i.e. babel plugin transform runtime remove console

run the command ----
npm install babel-plugin--trnsform-remove-console --save-dev

after install it we configure it in project  by using the :
 .bebelrc
 ==========================================================================================================
 
 
Reconsilation:-
 
/// The Diffing Algorithm
When diffing two trees, React first compares the two root elements. The behavior is different depending on the types of the root elements.
If you implement it naively, inserting an element at the beginning has worse performance. For example, converting between these two trees works poorly:

<ul>
  <li>Duke</li>
  <li>Villanova</li>
</ul>

<ul>
  <li>Connecticut</li>
  <li>Duke</li>
  <li>Villanova</li>
</ul>
React will mutate every child instead of realizing it can keep the <li>Duke</li> and <li>Villanova</li> subtrees intact. This inefficiency can be a problem.

Keys
In order to solve this issue, React supports a key attribute. When children have keys, React uses the key to match children in the original tree with children in the subsequent tree. For example, adding a key to our inefficient example above can make the tree conversion efficient:

<ul>
  <li key="2015">Duke</li>
  <li key="2016">Villanova</li>
</ul>

<ul>
  <li key="2014">Connecticut</li>
  <li key="2015">Duke</li>
  <li key="2016">Villanova</li>
</ul>
Now React knows that the element with key '2014' is the new one, and the elements with the keys '2015' and '2016' have just moved.

In practice, finding a key is usually not hard. The element you are going to display may already have a unique ID, so the key can just come from your data:

<li key={item.id}>{item.name}</li>



======================================================

react.createElement => object => html(DOM)


const heading =react.creatElement(
 



JSX- 

when we write in multiple line we can do it by using ();
e.g. 
    const heading2=(
      <h1 id="title" key="h2">
      Namaste React
      
      </h1>
    );

Que:-  Is jsx html inside javascript??
Ans:-  NO.
      <h1 id="title" key="h2">
      Namaste React
     </h1>
     
     jsx is html like syntax not html, this is fancy way write html inside javascript
     
     
     
react.createElement give us object, oject is inside heading and obj is render as a html in the dom

ques:-  who develop jsx---meta developer.


difference between html ans jsx?
1 we write in html small letter but in jsx use camel-case.
2    html--class     jsx-className


Ques-:how does execute?
ans-:   javacript does not understand the code of jsx , it is understand by babel.
babel is javascript library. babel takes ur code and gives u normal code.

babel is AST abstract syntax tree ,
it execute line by line . it is javascript compiler.

JSX=> React.createElement => Object => HTML(DOM)

ques:- how to create image in jsx?

---adv of jsx ====
1. readbility- it is most part  
2. syntax sugar, 
3. developer experience, 
4. maintaibility , 
5. less code.

-----when we write code , it  for human not machine. 

where isbebel , this is not in pkg where it is?
it is come from parcel.

 ques -: How many package.json - 1
and pkg lock.json     -  2 one we create and other is in node modules

where is all trasivity depencies present --- Node Module


--------------------------------------------------------------

React Componets:-
    there r two type components-- 
    1. Functional -new way
    2. class based -old way
    
fuunctional component:-
    it is javascript function that return some piece of jsx or react element.
    
    const HeaderComponent=()=>
    {
    return <h1> functional component</h1>;
    };
    
    
Note:-
      Name of component start with capital letter. but it is not mendetatory but its good practise to do this.
      functional component is normal function.



this ids normal javascript function that is returnning jsx

  const Hc1=()=>{
  return (
     <div>  
     <h1> namste react</h1>
     <h2> this is react</h2>
     </div>
     );
     };
     
  both r same.
  
   const Hc2=()=>(
     <div> 
     <h1> namste react</h1>
     <h2> this is react</h2>
     </div>
     );
     
     we can also write javascript normal function.
     
     const Hc1= function(){
  return (
     <div>  
     <h1> namste react</h1>
     <h2> this is react</h2>
     </div>
     );
     };
 this is valid.
    
Que:-How to we render my react element?
Ans:-
rea ct element -- its object 
const heading=(
<h1 id='title' key='h2'>
</h1>
);

render the react element---
    root.render(heading);
    
Que:- How to render react functional component?  
Ans:-
we do just like
root.render(<Hc1/>);
  
Ques:- how to use react element in react component?
Ans:-
<div>
      {heading}
      
 </div>

Ques:- how to use react component in react component?
Ans:-
<div>
      <Hc2/>
      also we write....   
      {Hc2()}
      
 </div>
 ===============================
 sanitization :- it is done by jsx
 
 call data from api.
 const data=api.getData();
 
 const Hc2=()=>(
     <div> 
     {data}.........> it does sanitization , data r not put directly iside it.
     <h1> namste react</h1>
     <h2> this is react</h2>
     </div>
     );
====================================     
Jargan:-   
          
  composing component or component composition--  when we use component inside component  known as component component.
  
  
All r roll up what r in lecture 4
---------------------------------
1. created script:-   "scripts":{
                      "start":"parcel index.html",
2.   build              
                       "build":"parcel build index.html "
                      };
                      
3. Remove console log  so install plugin and configure it in system.
   babel-plugin-transform-remove-console -D
   
   for configure-   .babelrc  by making file 
     file include code i.e.
       { 
       "plugin":[[" transform-remove-console",
       {exclude"":["error","warn"]}
        
        ]]
        }
4.  Browserlist :- last 2 version of chrome  and also on other browser
    "browserlist":{
    "last 2 version of chrome"
    };
           
5. Keys :-
    reconsillation 
    diffing algorithm
    
    we should always use unique key
    
6.  JSX:-    it uses react.createElement 

7. react element - its a normal variable jsx is assigned to it.
8. react component
9. composition component
10. skipped return from component

=================================================
doubt:--

why do we import react from react  
-> bcz react come from node modules.

will jsx work if parcel is not install as bbel dependencies in parcel?
->jsx dont work if parcel is not there,jsx need bbel, if u r not use parcel u dont use it you should have to use bbel,bcz bbl understand ur jsx.

what is best way to call functional component?
-> <ComponentName/> , it is best way.

if u using anyting that is parcel or webpack , and use jsx u need to bbel  bbel is come from what r u using.

is the component hoisted?
-> yes,it behave just like javascript function.

why will we need functional component?
-> when we  pass props to in function.

how jsx prevent excess?
->
why it is called api rather than function?
-> 
  const root= ReactDOM.createRoot(document.getElementById('root');
this is Jorgan . .createRoot is api, api is interface. 

why does 302 is direct happen when we import react from cdn?
-> bcz we including script tag its does not norml call, it is from index.js file so its tree as a network call so that why it just redirect there that is cdn. this is browser thing not react.

->parcel is zero config means when we start we do not need any thing to configure.

polyfill- babel transform automatically when code not work on browser what we use. use new and not use old 

clean code-> taake code, and make it to clear , by changing 
tree shaking-> remove unused code





    
           
                      
                      

  
  

