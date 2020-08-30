# Using SitePrism for page objects

SitePrism is an easy DSL for creating Page Objects that are the basis for functional testing.
See this example:

    class NewCommentPage < SitePrism::Page
      set_url '/studynotes/{/studynote}/comments/new'
    
      elements :comment_field, '#comment'
      element :submit_button, '#submit_form'
    end

Here I first define the URL for the Page and then the field on the page that I use for testing.
