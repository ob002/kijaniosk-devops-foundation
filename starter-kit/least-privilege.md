# IAM Least Privilege Design

## Scenario
The KijaniKiosk application needs to display product images to users. These images are stored in an AWS S3 Bucket named `kijanikiosk-product-images`.

## The Principle of Least Privilege
The application server should **only** be able to read images. It should **not** be able to delete images, change permissions, or access other buckets.

## IAM Policy Design
We will create an IAM Role named `KioskAppImageReaderRole` with the following JSON policy:

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:GetObject"
      ],
      "Resource": "arn:aws:s3:::kijanikiosk-product-images/*"
    }
  ]
}

### Explanation
- **Action:** `s3:GetObject` allows reading/downloading files. It explicitly denies `s3:DeleteObject` or `s3:PutObject`.
- **Resource:** It is scoped strictly to the specific bucket. If the app tries to access another bucket, it will be denied.
