# Using SitePrism for page objects

SitePrism is an easy DSL for creating Page Objects that are the basis for functional testing.
See this example:

    class NewCommentPage < SitePrism::Page
      set_url '/studynotes/{/studynote}/comments/new'
    
      elements :comment_field, '#comment'
      element :submit_button, '#submit_form'
    end

Here I first define the URL for the Page and then the field on the page that I use for testing.

In tests you can then use these page objects:

    let(:ssp) { ShowStudynotePage.new }
    let(:ncp) { NewCommentPage.new }
    let(:note) { create(:studynote) }
    
    ssp.load
    ncp.load(studynote: note.id)
    
ssp.load navigates to the ShowStudynotePage, so the elements are available for setting and getting etc.

ncp.load navigates to one specific CommentPage, the page belonging to this studynote.
