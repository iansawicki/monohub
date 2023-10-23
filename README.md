
aws ecr describe-images --registry-id 258175030240 --repository-name template-images --region us-east-1 --profile nimbus-dev \
--query 'imageDetails[*].{CreatedAt:imagePushedAt,imageTag:imageTag}' --output table


aws ecr describe-images --registry-id 258175030240 --repository-name template-images --region us-east-1 --profile nimbus-dev \
--query 'imageDetails[*].{ImageName:imageTags[0], CreatedDate:imagePushedAt}' --output table

# to a table


aws ecr describe-images --registry-id 258175030240 --repository-name template-images --region us-east-1 --profile nimbus-dev \
--query 'imageDetails[*].{ImageName:imageTags[0], CreatedDate:imagePushedAt}' --output json | jq -r '.[] | [.ImageName, .CreatedDate] | @csv' > image_metadata.csv
# monohub
