create a key-pair if don’t have one..

If for creating a key-pair

# Generate new private key 
resource "tls_private_key" "my_key" {
  algorithm = "RSA"
}

# Generate a key-pair with above key
resource "aws_key_pair" "deployer" {
  key_name   = "newkey-pair"
  public_key = tls_private_key.my_key.public_key_openssh
}

# Saving Key Pair for ssh login for Client if needed
resource "null_resource" "save_key_pair"  {
	provisioner "local-exec" {
	    command = "echo  ${tls_private_key.my_key.private_key_pem} > mykey.pem"
  	}
}
