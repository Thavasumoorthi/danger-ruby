
# Get the list of modified files
modified_files = git.modified_files

if modified_files.empty?
  warn("No files were modified.")
else
  message("Modified files: #{modified_files.join(', ')}")
end

# Check for "puts" statements in modified files
modified_files.each do |file|
  file_content = File.read(file) rescue nil  # Read file safely
  if file_content && file_content.include?("puts")
    fail("The file '#{file}' contains a 'puts' statement. Please remove it.")
  end
end
