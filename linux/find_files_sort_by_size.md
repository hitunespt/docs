#Find Files Sorted by Size
find /path/to/search -type f -name "*.jpg" -exec du -h {} + | sort -rh
