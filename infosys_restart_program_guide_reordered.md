# INFOSYS RESTART PROGRAM - COMPREHENSIVE INTERVIEW GUIDE 2025
# =======

**Document Structure:**
1. [Quick Reference Cheatsheets](#cheatsheets) (Start Here for Quick Reference)
2. [Profile & Focus Areas](#profile)
3. [Detailed Examples & Implementations](#examples)
4. [Interview Tips & Resources](#tips)

<a name="cheatsheets"></a>
# QUICK REFERENCE CHEATSHEETS
# =======

## PYTHON CHEATSHEET
```python
# Data Types
x = 5        # int
y = 3.14     # float
z = 1 + 2j   # complex

# Strings
s = "Hello"  # String operations
print(s[0])  # H (indexing)
print(s[1:]) # ello (slicing)

# Lists
lst = [1, 2, 3]
lst.append(4)    # Add element
lst.pop()        # Remove last
lst.sort()       # Sort list

# Dictionaries
d = {'key': 'value'}
d['new'] = 'item'    # Add item
del d['key']         # Delete item
d.get('key', None)   # Safe get

# Sets
s = {1, 2, 3}
s.add(4)        # Add element
s.remove(1)     # Remove element

# Control Flow
if condition:
    do_something()
elif other_condition:
    do_other()
else:
    do_default()

# Loops
for item in iterable:
    process(item)

while condition:
    do_something()

# List Comprehension
squares = [x**2 for x in range(10)]

# Functions
def greet(name="World"):
    return f"Hello, {name}!"

# Lambda
square = lambda x: x**2
```

## AWS CHEATSHEET
```bash
# S3 Commands
aws s3 ls                    # List buckets
aws s3 cp file.txt s3://bucket/  # Upload file
aws s3 sync . s3://bucket/   # Sync directory

# EC2 Commands
aws ec2 describe-instances   # List instances
aws ec2 start-instances     # Start instance
aws ec2 stop-instances      # Stop instance

# Lambda Commands
aws lambda list-functions   # List functions
aws lambda invoke --function-name myFunc output.txt  # Invoke

# Common Services
S3 (Storage):
- Object storage
- Versioning
- Lifecycle policies
- Access control

EC2 (Compute):
- Instance types
- AMIs
- Security groups
- Load balancing

Lambda (Serverless):
- Event triggers
- Function configuration
- Environment variables
- Execution roles
```

## LINUX COMMAND CHEATSHEET
```bash
# File Operations
ls -la          # List all
cd path         # Change directory
pwd             # Current directory
cp src dst      # Copy
mv src dst      # Move/rename
rm file         # Delete
chmod 755 file  # Permissions

# Text Processing
cat file        # View file
grep pattern    # Search text
sed 's/old/new' # Replace text
awk '{print $1}' # Process text

# Process Management
ps aux          # List processes
top             # Monitor processes
kill PID        # Kill process
fg             # Foreground
bg             # Background

# Network
ping host      # Test connection
netstat        # Network status
ifconfig       # Network config
curl URL       # HTTP request
```

## GIT CHEATSHEET
```bash
# Repository
git init              # Create new repo
git clone URL         # Clone repo
git remote -v         # List remotes

# Basic Commands
git status           # Check status
git add .            # Stage all
git commit -m "msg"  # Commit
git push origin main # Push
git pull            # Update

# Branching
git branch          # List branches
git checkout -b new # Create branch
git merge branch    # Merge
git rebase main    # Rebase

# History
git log            # View history
git diff           # View changes
git blame file     # Line history
```

## SQL CHEATSHEET
```sql
-- Basic Queries
SELECT column FROM table;
SELECT DISTINCT column FROM table;
SELECT * FROM table WHERE condition;

-- Joins
INNER JOIN  -- Common records
LEFT JOIN   -- All from left
RIGHT JOIN  -- All from right
FULL JOIN   -- All records

-- Aggregations
COUNT(*)    -- Count records
SUM(col)    -- Sum values
AVG(col)    -- Average
MAX(col)    -- Maximum
MIN(col)    -- Minimum

-- Grouping
GROUP BY column
HAVING count(*) > 1

-- Ordering
ORDER BY col1 ASC, col2 DESC
```

## SHELL SCRIPTING CHEATSHEET
```bash
# Basic Script Structure
#!/bin/bash
# Variables
NAME="John"
echo "Hello, $NAME"

# Control Structures
if [ $1 -gt 100 ]; then
    echo "Greater than 100"
fi

for i in {1..5}; do
    echo "Number: $i"
done

while [ $counter -le 5 ]; do
    ((counter++))
done

# Functions
check_file() {
    if [ -f "$1" ]; then
        echo "File exists"
    fi
}

# Common Examples
# Backup Script
timestamp=$(date +%Y%m%d_%H%M%S)
tar -czf "backup_$timestamp.tar.gz" "$src_dir"

# Process Monitor
if ! pgrep -x "$process_name" >/dev/null; then
    echo "Process not running!"
fi

# Health Check
echo "Memory Usage:"
free -h
df -h
uptime
```

## TERRAFORM CHEATSHEET
```hcl
# Basic Commands
terraform init      # Initialize
terraform plan     # Preview changes
terraform apply    # Apply changes
terraform destroy  # Cleanup

# Resource Block
resource "aws_type" "name" {
    attribute = value
}

# Variables
variable "name" {
    type = string
    default = "value"
}

# Output Values
output "name" {
    value = resource.attribute
}
```

<a name="profile"></a>
# PROFILE & FOCUS AREAS
# =======

## PROFILE OVERVIEW
- 8 years prior experience (TCS: COBOL, Unix, C)
- 8 years career break
- Target role: AWS + Python Developer
- Additional knowledge: Basic Terraform

## CORE FOCUS AREAS (Priority Order)
1. Python Programming (Primary)
2. AWS Services & Implementation
3. Linux/Unix Commands (Leveraging Your Background)
4. Git Version Control
5. SQL Basics
6. Terraform (Additional Knowledge)

<a name="examples"></a>
# DETAILED EXAMPLES & IMPLEMENTATIONS
# =======

## SECTION 1: BASIC PYTHON EXAMPLES (FUNDAMENTALS)

1. String Manipulation (Basic)
```python
def reverse_string(s):
    return s[::-1]

def count_vowels(s):
    vowels = 'aeiouAEIOU'
    return sum(1 for char in s if char in vowels)
```
Explanation:
- Basic string slicing [start:end:step]
- Common interview starter questions
- Shows Python syntax understanding

2. Number Operations (Basic)
```python
def is_prime(n):
    if n <= 1:
        return False
    for i in range(2, int(n ** 0.5) + 1):
        if n % i == 0:
            return False
    return True

def factorial(n):
    if n == 0 or n == 1:
        return 1
    return n * factorial(n - 1)
```
Explanation:
- Mathematical logic implementation
- Optimization techniques
- Recursion understanding

## SECTION 2: ADVANCED PYTHON EXAMPLES

1. Advanced String Operations
```python
def string_operations():
    # String compression
    def compress_string(s):
        if not s: return ""
        result = []
        count = 1
        current = s[0]
        for char in s[1:]:
            if char == current:
                count += 1
            else:
                result.extend([current, str(count)])
                current = char
                count = 1
        result.extend([current, str(count)])
        return "".join(result)
    
    # Check string rotations
    def are_rotations(s1, s2):
        if len(s1) != len(s2):
            return False
        return s2 in s1 + s1
    
    # Find palindromic substrings
    def palindromic_substrings(s):
        result = set()
        # Odd length palindromes
        for i in range(len(s)):
            left = right = i
            while left >= 0 and right < len(s) and s[left] == s[right]:
                result.add(s[left:right + 1])
                left -= 1
                right += 1
        
        # Even length palindromes
            left, right = i, i + 1
            while left >= 0 and right < len(s) and s[left] == s[right]:
                result.add(s[left:right + 1])
                left -= 1
                right += 1
        return list(result)
```

2. Advanced Data Structures
```python
# Linked List with Cycle Detection
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None
    
    def append(self, data):
        if not self.head:
            self.head = Node(data)
            return
        current = self.head
        while current.next:
            current = current.next
        current.next = Node(data)
    
    def detect_cycle(self):
        """Floyd's Cycle Detection Algorithm"""
        if not self.head:
            return False
        slow = fast = self.head
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
            if slow == fast:
                return True
        return False

# Binary Search Tree
class TreeNode:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None

class BinarySearchTree:
    def __init__(self):
        self.root = None
    
    def insert(self, data):
        if not self.root:
            self.root = TreeNode(data)
            return
        self._insert_recursive(self.root, data)
    
    def _insert_recursive(self, node, data):
        if data < node.data:
            if node.left is None:
                node.left = TreeNode(data)
            else:
                self._insert_recursive(node.left, data)
        else:
            if node.right is None:
                node.right = TreeNode(data)
            else:
                self._insert_recursive(node.right, data)
```

## SECTION 3: AWS EXAMPLES

1. Basic S3 Operations
```python
import boto3

def upload_to_s3(file_name, bucket, object_name=None):
    s3 = boto3.client('s3')
    if object_name is None:
        object_name = file_name
    try:
        s3.upload_file(file_name, bucket, object_name)
        return True
    except Exception as e:
        print(f"Upload failed: {e}")
        return False

def list_s3_objects(bucket):
    s3 = boto3.client('s3')
    try:
        response = s3.list_objects_v2(Bucket=bucket)
        return [obj['Key'] for obj in response.get('Contents', [])]
    except Exception as e:
        print(f"Error: {e}")
        return []
```

2. Basic Lambda Function
```python
def lambda_handler(event, context):
    """Basic S3 event processor"""
    for record in event['Records']:
        bucket = record['s3']['bucket']['name']
        key = record['s3']['object']['key']
        print(f"File {key} uploaded to bucket {bucket}")
    return {'statusCode': 200, 'body': 'Success'}
```

3. Complete S3 Operations Class
```python
import boto3
from botocore.exceptions import ClientError
import logging

class S3Operations:
    def __init__(self, region_name='us-west-2'):
        self.s3 = boto3.client('s3', region_name=region_name)
        self.logger = logging.getLogger(__name__)
    
    def create_bucket(self, bucket_name):
        try:
            self.s3.create_bucket(
                Bucket=bucket_name,
                CreateBucketConfiguration={'LocationConstraint': 'us-west-2'}
            )
            return True
        except ClientError as e:
            self.logger.error(e)
            return False
    
    def enable_versioning(self, bucket_name):
        try:
            self.s3.put_bucket_versioning(
                Bucket=bucket_name,
                VersioningConfiguration={'Status': 'Enabled'}
            )
            return True
        except ClientError as e:
            self.logger.error(e)
            return False
```

4. Advanced Lambda with Multiple Services
```python
def advanced_lambda_handler(event, context):
    """Lambda function integrating S3, DynamoDB, and SNS"""
    s3 = boto3.client('s3')
    dynamodb = boto3.resource('dynamodb')
    sns = boto3.client('sns')
    
    try:
        # Process S3 event
        bucket = event['Records'][0]['s3']['bucket']['name']
        key = event['Records'][0]['s3']['object']['key']
        
        # Log to DynamoDB
        table = dynamodb.Table('ProcessingLog')
        table.put_item(
            Item={
                'id': f"{bucket}/{key}",
                'timestamp': datetime.now().isoformat(),
                'status': 'processing'
            }
        )
        
        # Process file and notify
        sns.publish(
            TopicArn='arn:aws:sns:region:account-id:MyTopic',
            Message=f"Processed {key} in {bucket}"
        )
        
        return {'statusCode': 200, 'body': 'Success'}
    except Exception as e:
        return {'statusCode': 500, 'body': str(e)}
```

## SECTION 4: SQL EXAMPLES

1. Basic Queries
```sql
-- Basic SELECT
SELECT * FROM employees;
SELECT name, salary FROM employees WHERE salary > 50000;

-- Joins
SELECT e.name, d.department_name
FROM employees e
JOIN departments d ON e.dept_id = d.id;
```

2. Advanced Queries
```sql
-- Complex JOIN with subquery
SELECT 
    e.employee_name,
    d.department_name,
    (SELECT COUNT(*) 
     FROM employees sub 
     WHERE sub.department_id = e.department_id 
     AND sub.salary > e.salary) as higher_paid_colleagues
FROM 
    employees e
    JOIN departments d ON e.department_id = d.id;

-- Window Functions
SELECT 
    employee_name,
    salary,
    department_id,
    RANK() OVER (PARTITION BY department_id ORDER BY salary DESC) as salary_rank
FROM 
    employees;
```

3. Data Modification Queries
```sql
-- INSERT Examples
-- Single row insert
INSERT INTO employees (name, department_id, salary)
VALUES ('John Doe', 1, 60000);

-- Multiple row insert
INSERT INTO employees (name, department_id, salary)
VALUES 
    ('Jane Smith', 2, 65000),
    ('Bob Wilson', 1, 55000);

-- INSERT with SELECT
INSERT INTO employee_archive
SELECT * FROM employees 
WHERE termination_date IS NOT NULL;

-- UPDATE Examples
-- Basic update
UPDATE employees
SET salary = 65000
WHERE employee_id = 101;

-- Update with calculations
UPDATE employees
SET salary = salary * 1.1
WHERE department_id = 2;

-- Update with subquery
UPDATE employees
SET salary = salary * 1.15
WHERE department_id IN (
    SELECT department_id
    FROM departments
    WHERE performance_rating > 4
);

-- DELETE Examples
-- Basic delete
DELETE FROM employees
WHERE employee_id = 101;

-- Delete with subquery
DELETE FROM employees
WHERE department_id IN (
    SELECT department_id
    FROM departments
    WHERE is_active = false
);

-- Delete with JOIN condition
DELETE e
FROM employees e
JOIN departments d ON e.department_id = d.id
WHERE d.is_disbanded = true;

-- TRUNCATE (Delete all records)
TRUNCATE TABLE temporary_logs;
```

## SECTION 5: TERRAFORM EXAMPLES

Basic AWS Provider and S3 Bucket
```hcl
provider "aws" {
    region = "us-west-2"
}

resource "aws_s3_bucket" "example" {
    bucket = "my-terraform-bucket"
    
    versioning {
        enabled = true
    }
    
    tags = {
        Environment = "Dev"
        Project     = "Demo"
    }
}
```

<a name="tips"></a>
# INTERVIEW TIPS & RESOURCES
# =======

## INTERVIEW PREPARATION TIPS

1. Technical Interview Approach
- Start with clarifying questions
- Think aloud while solving problems
- Discuss time/space complexity
- Consider edge cases
- Write clean, commented code

2. AWS Discussion Points
- Core services (EC2, S3, Lambda)
- Security best practices
- High availability concepts
- Cost optimization
- Serverless architecture

3. Career Break Discussion
- Be confident about your break
- Highlight any learning during break
- Show enthusiasm for technology
- Emphasize transferable skills
- Connect past experience to current role

4. Your Unique Selling Points
- Strong Unix/COBOL background
- Systematic problem-solving approach
- Experience with legacy systems
- Understanding of batch processing
- Ability to bridge old and new technologies

## ADDITIONAL RESOURCES

1. Online Learning
- Python: https://docs.python.org/3/
- AWS: https://aws.amazon.com/training/
- Git: https://git-scm.com/doc
- SQL: https://mode.com/sql-tutorial/
- Linux: https://linuxjourney.com/

2. Practice Platforms
- LeetCode for coding practice
- AWS Free Tier for hands-on
- GitHub for version control practice
- HackerRank for SQL practice

Remember:
- Focus on Python and AWS primarily
- Leverage your Unix background
- Show enthusiasm for learning
- Connect past experience to current technologies
- Be confident about your career transition

Good luck with your Infosys Restart Program interview! 🚀
# =======