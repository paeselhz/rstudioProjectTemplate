#' This package will create a function called create_project()
#'
#' It's callback is at: inst/rstudio/templates/project/create_project.dcf
#'
#' @export

create_project <-
  function(path, ...) {

    # Create the project path given the name chosen by the user:
    dir.create(path, recursive = TRUE, showWarnings = FALSE)

    # Change the working directory to the recently created folder:
    setwd(file.path(getwd(), path))

    # Collect the list of inputs in a list to be called later:
    dots <- list(...)

    # In the project template we've added 2 choices for the user:
	# * One allows them to select if the project will have a .gitignore file
	# * The other will create a folder, given a select input from the user

	# Check .gitignore argument
	if(dots[["createGitignore"]]) {
		  git_ignores <-
    			c(
			      '.Rhistory',
			      '.Rapp.history',
      			  '.RData',
			      '.Ruserdata',
			      '.Rproj.user/',
			      '.Renviron'
			 )

		  writeLines(paste(git_ignores, sep = '\n'), '.gitignore')
		}

	# Check selected folder
	if(dots[["folder"]] == "Production"){
		dir.create("production", recursive = TRUE, showWarnings = FALSE)
	} else {
		dir.create("development", recursive = TRUE, showWarnings = FALSE)
	}

}
