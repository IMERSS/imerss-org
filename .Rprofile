# REMEMBER to restart R after you modify and save this file!

# First, execute the global .Rprofile if it exists. You may configure blogdown
# options there, too, so they apply to any blogdown projects. Feel free to
# ignore this part if it sounds too complicated to you.
if (file.exists("~/.Rprofile")) {
  base::sys.source("~/.Rprofile", envir = environment())
}

# Now set options to customize the behavior of blogdown for this project. Below
# are a few sample options; for more options, see
# https://bookdown.org/yihui/blogdown/global-options.html
options(
  # to automatically serve the site on RStudio startup, set this option to TRUE
  blogdown.serve_site.startup = FALSE,
  # to disable knitting Rmd files on save, set this option to FALSE
  blogdown.knit.on_save = TRUE,
  # build .Rmd to .md; to build to .html (via Pandoc), set this option to 'html'
  blogdown.method = 'markdown'
)

# 1. Define the required Hugo version
options(blogdown.hugo.version = "0.121.0")

# 2. Automatically check and download if missing
if (interactive() && requireNamespace("blogdown", quietly = TRUE)) {
  target_version <- getOption("blogdown.hugo.version")

  # Check if the exact target version is already installed locally
  installed_versions <- blogdown::find_hugo("all")

  if (!target_version %in% installed_versions) {
    message(paste0("ℹ [blogdown] Required Hugo v", target_version, " not found locally."))
    message("📥 Automatically installing Hugo v", target_version, "...")

    tryCatch({
      blogdown::install_hugo(version = target_version)
      message("✅ Hugo installation complete!")
    }, error = function(e) {
      warning("❌ Automatic Hugo installation failed. Please run blogdown::install_hugo('", target_version, "') manually.")
    })
  }
}
