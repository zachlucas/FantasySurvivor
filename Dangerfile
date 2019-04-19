# Warn when there is a big PR
warn "Big PR, consider splitting into smaller" if git.lines_of_code > 500

message("Hello, Danger is covering this PR")

# Mainly to encourage writing up some reasoning about the PR, rather than
# just leaving a title
if github.pr_body.length < 5
  fail "Please provide a summary in the Pull Request description"
end


podfile_updated = !git.modified_files.grep(/Podfile/).empty?

# Leave warning if Podfile changes
if podfile_updated
  warn "The `Podfile` was updated"
end


# Warn when there is no IODA in the title
warn "No IODA in PR title" if !(github.pr_title.include? "IODA-")
