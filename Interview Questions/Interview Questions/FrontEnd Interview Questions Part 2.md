# FrontEnd Interview Questions Part 2

Created By: Chris Trinh
Last Edited: Jan 17, 2020 3:22 PM

HTML

- What does a `doctype` do?
    - Stands for document type declaration
    - Informs web browser the type and version of html used for building the document. Each version of HTML has its own rules and properties
- How do you serve a page with content in multiple languages?
    1. Explicitly choose the preferred language
        1. language selection mechanism; using cookies to store selected language in current session like cookies
    2. Make the best guess based on existing data
        1. special 'accept-language request header to get the preference
        2. `Accept-Language: fr-CH, fr;q=0.9, en;q=0.8, de;q=0.7, *;q=0.5`
    3. After one of the two is done, we need to specify a char set for each language
    4. Optimize SEO because theres a lot of duplicated contents so canonical URL
        1. Technical solution for duplicate content, where you choose one URL to show the content
- What kind of things must you be wary of when designing or developing for multilingual sites?
    - Machine Translation
        - Text translations could be messed up per language
    - Changing Language Options UI
        - pick a place to allow easy access to change language
    - Culture Awareness
        - design of website might not fit a certain cultures perspectives
    - Content Organization
        - Some countries have people writing from right to left and vice versa, needs to be universal.
    - Encoding Special Characters
    - Duplicate Content
    - Dates and Orthography
    - No words of SEO
- What are `data-` attributes good for?
    - Allows storage of extra information on standard HTML elements without using non-standard attributes, extra properties on DOM, or Node
- Consider HTML5 as an open web platform. What are the building blocks of HTML5?
    - Tags, tags that surrounds content and apply meaning using `<` and `>` brackets
    - Attributes, provides extra information about the element , `name` and `value`
- Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.
- Describe the difference between `<script>`, `<script async>` and `<script defer>`.
- Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?
- What is progressive rendering?
- Why you would use a `srcset` attribute in an image tag? Explain the process the browser uses when evaluating the content of this attribute.
- Have you used different HTML templating languages before?