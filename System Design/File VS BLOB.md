To store a image or any file why we sould use File not Database BLOB?
  1. Mutability : For Image or any file we do not need mutability. User can upload same file with little diffrently. So mutabilty is not required which provide by DBs.
  2. Transaction : Files doesn't required transaction garantiy.
  3. Index Search : Which is not applicable for image or any file search
  4. Access Control : This is alos not important and it can be handled in a file management.

Advantages of Using File
  - Cheaper
  - Faster
  - CDN first access
