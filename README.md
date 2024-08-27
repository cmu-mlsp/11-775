# Course Website for 11-775, Fall 2024

## Note for Development

Use the following command to serve the website locally:
```bash
docker run -it --rm --network=host -v $(pwd):/site kashu98/jekyll-serve
```

## For Future Instructors

Create a new branch for each semester as `website<year><semester>` (e.g., `website2024fa`, `website2025sp`, etc.)., and update the content accordingly.


### Where to Update
- Announcements: `_announcements/*.md`
- Assignments: `_assignments/*.md`
- Lectures: `_lectures/*.md`
- Events: `_events/*.md`
- People: `_data/people.yml`


### Archive Previous Semester's Website

Create a directory `archive` to store the previous semester's website.
Inside the `archive` directory, put the generated `_site` directory from the previous semester's website as `<year><semester>`.

- Note that when generating the `_site` directory for each year, make sure to remove archive directory to avoid recursive copying.
- Relative path in the `archive` might be broken, so make sure to update the path accordingly.
- Should we automate this process with GitHub Actions?
    - create a deploy branch
    - mkdir archive
    - for each branch in the repo
        - jekyll build
        - replace all the relative path in _site
        - move _site to archive/<year><semester>
    - build the current website
